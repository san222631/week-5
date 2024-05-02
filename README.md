# week-5
Project Description
在command prompt練習MySQL的各種指令，生成一個database-"website"，這個database底下有2個tables - "member" & "message"。

## **TASK 2**    
### Q1  
```CREATE DATABASE website;```    
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

## **TASK 3**  
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
- 'UPDATE member  
SET name = 'test2'  
WHERE username = 'test';'  
![Alt text](/12.jpg)

## **TASK 4**  
- 'SELECT COUNT(*) FROM member;'  
![Alt text](/13.jpg)
- 'SELECT SUM(follower_count) FROM member;'  
![Alt text](/14.jpg)
- 'SELECT AVG(follower_count) FROM member;'  
![Alt text](/15.jpg)
- 'SELECT AVG(follower_count) AS avg_f_c
FROM (  
SELECT follower_count  
FROM member  
ORDER BY follower_count DESC  
LIMIT 2  
) AS top_two;'  
![Alt text](/16.jpg)

## **TASK 5**  
- 'CREATE TABLE message (  
id BIGINT NOT NULL PRIMARY KEY AUTO_INCREMENT,    
member_id BIGINT NOT NULL,  
content VARCHAR(255) NOT NULL,  
like_count INT UNSIGNED NOT NULL DEFAULT 0,  
time DATETIME NOT NULL DEFAULT NOW() ON UPDATE NOW(),  
FOREIGN KEY (member_id) REFERENCES member(id)    
);    
![Alt text](/17.jpg)
- 'SELECT    
m.id,    
m.member_id,  
m.content,  
m.like_count,  
m.time,  
mb.name AS sender_name  
FROM  
message m   
JOIN  
member mb    
ON    
m.member_id = mb.id;'  
![Alt text](/18.jpg)
- 'SELECT    
m.id,    
m.member_id,  
m.content,  
m.like_count,  
m.time,  
mb.name AS sender_name  
FROM  
message m   
JOIN  
member mb ON m.member_id = mb.id      
WHERE      
mb.username = 'test';'  
![Alt text](/19.jpg)
- 'SELECT AVG(like_count) AS avg_l_c
FROM (
SELECT
m.member_id,  
m.like_count,  
mb.name AS sender_name  
FROM  
message m   
JOIN  
member mb ON m.member_id = mb.id      
WHERE      
mb.username = 'test';'  
![Alt text](/20.jpg)
- 'SELECT  
mb.username,  
AVG(m.like_count) AS average_like_count  
FROM  
message m  
JOIN  
member mb ON m.member_id = mb.id  
GROUP BY  
mb.username;'
![Alt text](/21.jpg)




  
            
