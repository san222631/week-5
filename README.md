# week-5
Project Description
在command prompt練習MySQL的各種指令，生成一個database-"website"，這個database底下有2個tables - "member" & "message"。

##Task 2
1.'CREATE DATABASE website;'  
![Alt text](/1.jpg)
2.'CREATE TABLE member (  
id BIGINT PRIMARY KEY AUTO-INCREMENT UNIQUE,  
name VARCHAR(255) NOT NULL,  
username VARCHAR(255) NOT NULL,  
password VARCHAR(255) NOT NULL,  
follower_count INT UNSIGNED NOT NULL DEFAULT 0,
time DATETIME NOT NULL DEFAULT NOW() ON UPDATE NOW()
);'  
![Alt text](/2.jpg)  
![Alt text](/3.jpg)  
3. 
