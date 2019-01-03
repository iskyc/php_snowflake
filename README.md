# php_snowflake

## 描述
项目修改自Sxdd的[php_snowflake](https://github.com/Sxdd/php_snowflake)

因发现Sxdd的`php_snowflake`实现方式不太符合我们项目的需求,所以稍微修改了下。
最终返回结果是将8个字节的数字转换成16进制的大写字符串(如:5A04743296001001).


## 要求
* PHP >= 5.6 64位 (5.5以下的自己测试)
* Linux

```
63 62　　　　　 　    21　　　　　　        11　　　    0
---+----------------+-------------------+----------+
00 |timestamp(ms)   | service_no 　     | sequence |
---+----------------+-------------------+----------+
```

## 编译安装
```
phpize
./configure --with-php-config=/you/phppath/php-config
make
make install
```
## 例子
注意：$service_no的取值范围是:0~1023
```
$service_no = 1;
for ($i=0; $i < 10; $i++) { 
        echo PhpSnowFlake::nextId($service_no)."<br/>";
}
/*
5A04743296001001
5A04743296001002
5A04743296001003
5A04743296001004
5A04743296001005
5A04743296001006
5A04743296001007
5A04743296001008
5A04743296001009
*/
```
## License
Copyright (c) 2016 by [Towers](http://towers.pub) released under MIT License.


