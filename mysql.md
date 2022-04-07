##in mysql 

CREATE TABLE test ( 

     id INT,

     regular_expression TEXT CHARACTER SET utf8,

     sample TEXT CHARACTER SET utf8,

     sample_language TEXT CHARACTER SET utf8, 

     last_modified_date TEXT CHARACTER SET utf8,

     application_id INT,

     sms_category_id INT,

     enabled_for_matching INT,

     PRIMARY KEY (id)

);

select * from test;

select * from test where id='7616';

 
