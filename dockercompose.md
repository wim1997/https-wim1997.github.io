#dockercompose.yml

version: '3.3'

services:

  mysql:

    container_name: mysql

    image: 'mysql:8'

    restart: always
    ports:

      - "3306:3306"

    volumes:

      - /var/data/mysql:/var/lib/mysql

      - /etc/mysql:/etc/mysql

      - ./mysql-files:/var/lib/mysql-files


    environment:
      MYSQL_ROOT_PASSWORD: zadi1997

      MYSQL_DATABASE: wim

      MYSQL_USER: wim

      MYSQL_PASSWORD: zadi1997




~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               
~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

~                                                                                                                                               

"docker-compose.yml" 21L, 395C                                                                                                19,0-1        All

