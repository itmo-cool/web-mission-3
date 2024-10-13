# Mission 3

## Part1
https://drive.google.com/file/d/1i85Z5z3oV0WGio0JvZj5FRiNlPmDajxn/view?usp=sharing

## Part2
https://drive.google.com/file/d/1mQIUUPBQNfHZDswdmjljfftxuVmVT2G7/view?usp=sharing

## Part3
1.
```
SELECT username FROM USERS;
```

2.
```
SELECT users.username, COUNT(messages.id) AS message_count
FROM  users
LEFT JOIN messages ON users.id = messages.from
GROUP BY users.id, users.username;
```

3.
```
SELECT users.username, COUNT(messages.id) AS message_count
FROM users
LEFT JOIN messages ON users.id = messages.from
GROUP BY users.id, users.username
ORDER by message_count DESC Limit 1;
```
4.
```
SELECT AVG (message_count) AS average_messages FROM
(
SELECT users.id, COUNT (messages.id) AS message_count FROM users
LEFT JOIN messages ON users.id = messages.from    
GROUP BY users.id
) 
AS user_message_counts;
```
