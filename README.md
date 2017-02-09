# docker-db2
A DB2 docker that automatically creates a sample db.

## Getting started
You will need to have `docker-compose` installed.

 To start the DB2 docker:
 ```bash
 $ docker-compose up
 ```
 Wait for the image to be downloaded, built and started.
 
 ## Using the docker image
 You can use your database viewer with the properties below to connect to the DB and check:
 ```xml
 <url>jdbc:db2://localhost:50000/sample</url>
 <user>db2inst1</user>
 <password>password</password>
 ```
 or you can use the command below to get to the container shell:
 ```bash
 $ docker exec -it jdbc_db2_1 /bin/bash
 ```
 Switch user to `db2inst1`:
 ```bash
 $ su db2inst1
 ```
 Connect to our sample database:
 ```bash
 $ db2 connect to sample
 ```
 Run the script you want:
 ```bash
 $ db2 "select * from access_event"
 ```
 
 ## Initialize docker with scripts
 Put your create table script within `/ibm-db2/db2.sql` and the script will be run after database initialization