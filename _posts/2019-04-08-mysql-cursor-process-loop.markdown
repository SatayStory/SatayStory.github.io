---
layout: post
title:  "mysql的游标存储过程循环"
date:   2019-04-08 09:00:00 +0800
categories: code
---
#### mysql的游标存储过程循环

```mysql
delimiter $$
create procedure procedure11()
BEGIN
     DECLARE number INT DEFAULT 0;
		 DECLARE Done INT DEFAULT 0;
	   DECLARE rs CURSOR FOR SELECT DISTINCT textbook_id FROM	textbook_description;
     DECLARE CONTINUE HANDLER FOR SQLSTATE '02000' SET Done = 1;
     OPEN rs;
     FETCH NEXT FROM rs INTO number;
     REPEAT
	   IF NOT Done THEN
	     INSERT INTO textbook_description (textbook_id,desc_code,desc_value,create_time,create_user)VALUES(number,'CATALOGID','5',NOW(),'0');
	   END IF;
     FETCH NEXT FROM rs INTO number;
	   UNTIL Done END REPEAT;
     CLOSE rs;
END $$
```
---