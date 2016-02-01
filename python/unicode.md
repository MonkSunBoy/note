#unicode

## 将unicode point转换成它的显示

``` python
➜ /home/monkboy/文档/python >python3.4
Python 3.4.2 (default, Oct  8 2014, 10:45:20) 
[GCC 4.9.1] on linux
Type "help", "copyright", "credits" or "license" for more information. 
>>> str.encode(u'\u0022')
b'"'
>>> str.encode(u'\u0026')
b'&'
>>> str.encode(u'\u0027')
b"'"
```

