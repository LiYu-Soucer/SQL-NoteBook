# some fundamental tips:  
### Q: how to use sql in a other kinds of coding language?  
A: //创建语句  
   MySqlCommand cmd = new MySqlCommand("insert into user set username='" + username + "'" + ",password='"+password+"'",conn);  
   //执行语句  
   cmd.ExecuteNonQuery();  
   
The error-#1046 - No database selected
can occur when we are creating a table, but forget to select the database. 
so how can we select the database:
>use business    

!business is the name of your chosen database.
After using database ‘business’, we can create the above table and we will not get any error:  
>
mysql> CREATE table TblUni  
-> (  
-> id int,  
-> Name varchar(100)  
-> );    
Query OK, 0 rows affected (0.50 sec)

You need to know that:
1.SQL have to use uppercase letter
2.you have to choose a database, and be careful: database means a 存储数据的表的仓库而不是存储数据的表，即我们还是要创建表table

IN 与 = 的异同

 相同点：均在WHERE中使用作为筛选条件之一、均是等于的含义
 不同点：IN可以规定多个值，等于规定一个值
IN

SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1,value2,...);
