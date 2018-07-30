---
title: PHP链接数据库
date: 2018-01-10 15:29:43
tags:
- PHP
categories:
- PHP
---



<!--more-->

`index.php`

```php
<!DOCTYPE html>
<html>
<body>
<h3>PHP连接数据库start</h3>
<?php
  echo "w3shcool";
?>


    
<?php
    echo "Start";
$con = mysql_connect("localhost","root","root");
if (!$con)
  {
    echo "ERROR";
  die('Could not connect: ' . mysql_error());
  }
else {
    echo "YES";
}
if (mysql_query("CREATE DATABASE my_db2",$con))
  {
  echo "Database created";
  }
else
  {
  echo "Error creating database: " . mysql_error();
  }

mysql_close($con);
?>
    
    <h3>PHP连接数据库end</h3>
    
    
    
</body>
</html>
```



