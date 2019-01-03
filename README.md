# php_snowflake

## What is php_snowflake?

Twitter distributed ID generating Algorithm [SnowFlake](https://github.com/twitter/snowflake) PHP implementation version.

## Requires
* PHP >= 5.6  (Below 5.5 self-testing)
* Linux

```
63　62　　　　　 　   21　　　　　　    11　　　   0
---+----------------+-------------------+----------+
00 |timestamp(ms)  | service_no 　  | sequence |
---+----------------+-------------------+----------+
```

## Installation
```
phpize
./configure --with-php-config=/you/phppath/php-config
make
make install
```
## Example
Attention： Interval of $service_no in the range of 0-1023. Beyond that scope, PHP will report a fatal mistake.
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


