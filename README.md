# week-5
Project Description
在command prompt練習MySQL的各種指令，生成一個database-"website"，這個database底下有2個tables - "member" & "message"。

##**TASK 2**    
- 'CREATE DATABASE website;'  
![Alt text](/1.jpg)
- 'CREATE TABLE member (  
id BIGINT PRIMARY KEY AUTO-INCREMENT UNIQUE,  
name VARCHAR(255) NOT NULL,  
username VARCHAR(255) NOT NULL,  
password VARCHAR(255) NOT NULL,  
follower_count INT UNSIGNED NOT NULL DEFAULT 0,  
time DATETIME NOT NULL DEFAULT NOW() ON UPDATE NOW()
);'  
![Alt text](/2.jpg)  
![Alt text](/3.jpg)  

#**#TASK 3**  
- 'INSERT INTO member (name, username, password) VALUES ('test', 'test', 'test');'
![Alt text](/4.jpg)  
'INSERT INTO member (name, username, password)  
VALUES
('1Ting', 'ting', 'tingting'),  
('2Pieter', 'pieter', 'pp'),  
('3Mary', 'mary', 'mm'),  
('4Bob', 'bob', 'bb');'  
![Alt text](/5.jpg)
- 'SELECT * FROM member;'  
![Alt text](/6.jpg)
- 'SELECT * FROM member ORDER BY time DESC;'
![Alt text](/7.jpg)
- 'SELECT * FROM member
ORDER BY time DESC  
LIMIT 1, 3;'
![Alt text](/8.jpg)
- 'SELECT * FROM member WHERE username = 'test';'
![Alt text](/9.jpg)
- 'SELECT * FROM member WHERE name LIKE '%es%';'
![Alt text](/10.jpg)
- 'SELECT * FROM member
WHERE username ='test' AND password = 'test';'
![Alt text](/11.jpg)
            
