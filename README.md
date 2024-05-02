# week-5
#### Project Description:
#### 在command prompt練習MySQL的各種指令，生成一個database-"website"，這個database底下有2個tables - "member" & "message"。

## **TASK 2**    
### Q1.  
#### SQL Command
```
CREATE DATABASE website;
```
#### Result
![Alt text](/1.jpg)  
### Q2.
#### SQL Command
```
CREATE TABLE member (  
id BIGINT PRIMARY KEY AUTO-INCREMENT UNIQUE,  
name VARCHAR(255) NOT NULL,  
username VARCHAR(255) NOT NULL,  
password VARCHAR(255) NOT NULL,  
follower_count INT UNSIGNED NOT NULL DEFAULT 0,  
time DATETIME NOT NULL DEFAULT NOW() ON UPDATE NOW()
);
```
#### Result
![Alt text](/2.jpg)  
![Alt text](/3.jpg)  


## **TASK 3**  
### Q1-1.  
#### SQL Command
```
INSERT INTO member (name, username, password) VALUES ('test', 'test', 'test');
```
#### Result
![Alt text](/4.jpg) 
### Q1-2.  
#### SQL Command
```
INSERT INTO member (name, username, password)  
VALUES
('1Ting', 'ting', 'tingting'),  
('2Pieter', 'pieter', 'pp'),  
('3Mary', 'mary', 'mm'),  
('4Bob', 'bob', 'bb');
```
#### Result
![Alt text](/5.jpg)
### Q2.  
#### SQL Command
```
SELECT * FROM member;  
```
#### Result
![Alt text](/6.jpg)
### Q3.  
#### SQL Command
```
SELECT * FROM member ORDER BY time DESC;
```
#### Result
![Alt text](/7.jpg)
### Q4.  
#### SQL Command
```
SELECT * FROM member
ORDER BY time DESC  
LIMIT 1, 3;  
```
#### Result
![Alt text](/8.jpg)
### Q5.  
#### SQL Command
```
SELECT * FROM member WHERE username = 'test';
```
#### Result
![Alt text](/9.jpg)
### Q6.  
#### SQL Command
```
SELECT * FROM member WHERE name LIKE '%es%';
```
#### Result
![Alt text](/10.jpg)
### Q7.  
#### SQL Command
```
SELECT * FROM member
WHERE username ='test' AND password = 'test';
```
#### Result
![Alt text](/11.jpg)
### Q8.  
#### SQL Command
```
UPDATE member  
SET name = 'test2'  
WHERE username = 'test';
```
#### Result
![Alt text](/12.jpg)


## **TASK 4**
### Q1.  
#### SQL Command
```
SELECT COUNT(*) FROM member;
```
#### Result
![Alt text](/13.jpg)
### Q2.  
#### SQL Command
```
SELECT SUM(follower_count) FROM member;
```
#### Result
![Alt text](/14.jpg)
### Q3.  
#### SQL Command
```
SELECT AVG(follower_count) FROM member;
```
#### Result
![Alt text](/15.jpg)
### Q4.  
#### SQL Command
```
SELECT AVG(follower_count) AS avg_f_c
FROM (  
SELECT follower_count  
FROM member  
ORDER BY follower_count DESC  
LIMIT 2  
) AS top_two;
```
#### Result
![Alt text](/16.jpg)

## **TASK 5**  
### Q1.  
#### SQL Command
```
CREATE TABLE message (  
id BIGINT NOT NULL PRIMARY KEY AUTO_INCREMENT,    
member_id BIGINT NOT NULL,  
content VARCHAR(255) NOT NULL,  
like_count INT UNSIGNED NOT NULL DEFAULT 0,  
time DATETIME NOT NULL DEFAULT NOW() ON UPDATE NOW(),  
FOREIGN KEY (member_id) REFERENCES member(id)    
);
```
#### Result
![Alt text](/17.jpg)
### Q2.  
#### SQL Command
```
SELECT    
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
m.member_id = mb.id;
```
#### Result
![Alt text](/18.jpg)
### Q3.  
#### SQL Command
```
SELECT    
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
mb.username = 'test';
```
#### Result 
![Alt text](/19.jpg)
### Q4.  
#### SQL Command
```
SELECT AVG(like_count) AS avg_l_c
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
mb.username = 'test';
```
#### Result
![Alt text](/20.jpg)
### Q5.  
#### SQL Command
```
SELECT  
mb.username,  
AVG(m.like_count) AS average_like_count  
FROM  
message m  
JOIN  
member mb ON m.member_id = mb.id  
GROUP BY  
mb.username;
```
#### Result
![Alt text](/21.jpg)




  
            
