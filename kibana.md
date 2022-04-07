#kibana

##Step 1 — Installing and Configuring Elasticsearch

curl -fsSL https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -

sudo apt update

sudo apt install elasticsearch

sudo nano /etc/elasticsearch/elasticsearch.yml


The elasticsearch.yml file provides configuration options for your cluster, node, paths, memory, network, discovery, and gateway. Most of these options are preconfigured in the file but you can change them according to your needs. For the purposes of our demonstration of a single-server configuration, we will only adjust the settings for the network host.

. . .

---------------------------------- Network -----------------------------------

 Set the bind address to a specific IP (IPv4 or IPv6):

network.host: localhost

. . .

sudo systemctl start elasticsearch

sudo systemctl enable elasticsearch

curl -X GET "localhost:9200"

##Step 2 — Installing and Configuring the Kibana Dashboard

sudo apt install kibana

sudo systemctl enable kibana

sudo systemctl start kibana

echo "kibanaadmin:`openssl passwd -apr1`" | sudo tee -a /etc/nginx/htpasswd.users

sudo nano /etc/nginx/sites-available/your_domain

server {
    
    listen 80;

    server_name your_domain;

    auth_basic "Restricted Access";
    
    auth_basic_user_file /etc/nginx/htpasswd.users;

    location / {
    
        proxy_pass http://localhost:5601;
    
        proxy_http_version 1.1;
    
        proxy_set_header Upgrade $http_upgrade;
    
        proxy_set_header Connection 'upgrade';
    
        proxy_set_header Host $host;
    
        proxy_cache_bypass $http_upgrade;
    
    }
}

sudo ln -s /etc/nginx/sites-available/your_domain /etc/nginx/sites-enabled/your_domain

sudo nginx -t

sudo systemctl reload nginx

sudo ufw allow 'Nginx Full'

sudo ufw delete allow 'Nginx HTTP'


Kibana is now accessible via your FQDN or the public IP address of your Elastic Stack server. You can check the Kibana server’s status page by navigating to the following address and entering your login credentials when prompted:

http://your_domain/status

##Step 3 — Installing and Configuring Logstash

sudo nano /etc/logstash/conf.d/02-beats-input.conf

sudo apt install logstash

sudo nano /etc/logstash/conf.d/02-beats-input.conf


Insert the following input configuration. This specifies a beats input that will listen on TCP port 5044.

input {
  beats {
    port => 5044
  }
}

Next, create a configuration file called 30-elasticsearch-output.conf:

sudo nano /etc/logstash/conf.d/30-elasticsearch-output.conf

Insert the following output configuration. Essentially, this output configures Logstash to store the Beats data in Elasticsearch, which is running at localhost:9200, in an index named after the Beat used. The Beat used in this tutorial is Filebeat:

output {
  
  if [@metadata][pipeline] {

	elasticsearch {

  	hosts => ["localhost:9200"]

  	manage_template => false

  	index => "%{[@metadata][beat]}-%{[@metadata][version]}-%{+YYYY.MM.dd}"

  	pipeline => "%{[@metadata][pipeline]}"

	}

  } else {

	elasticsearch {

  	hosts => ["localhost:9200"]

  	manage_template => false

  	index => "%{[@metadata][beat]}-%{[@metadata][version]}-%{+YYYY.MM.dd}"

	}

  }
}

sudo -u logstash /usr/share/logstash/bin/logstash --path.settings /etc/logstash -t

sudo systemctl start logstash

sudo systemctl enable logstash