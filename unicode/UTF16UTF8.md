# UTF-16转UTF-8

根据unicode标准
[Unicode](https://en.wikipedia.org/wiki/Unicode)
[UTF-16](https://en.wikipedia.org/wiki/UTF-16)
[UTF-8](https://en.wikipedia.org/wiki/UTF-8)

```
Code points in the range U+D800–U+DBFF (1,024 code points) are known as high-surrogate code points, and code points in the range U+DC00–U+DFFF (1,024 code points) are known as low-surrogate code points. A high-surrogate code point (also known as a leading surrogate) followed by a low-surrogate code point (also known as a trailing surrogate) together form a surrogate pair used in UTF-16 to represent 1,048,576 code points outside BMP. High and low surrogate code points are not valid by themselves. Thus the range of code points that are available for use as characters is U+0000–U+D7FF and U+E000–U+10FFFF (1,112,064 code points). The value of these code points (i.e., excluding surrogates) is sometimes referred to as the character's scalar value.
```

转换过程如下
```
U+D83D U+DC23                                                  (16进制)(UTF-16)
55357  56355                                                   (10进制)
1101100000111101          1101110000100011                     (2进制)
11011000001111011101110000100011                               (拼成一个4byte的无符号整数)
      0000111101      0000100011                               减去 110110 和 110111
00001111010000100011                                           拼成一个整数
00011111010000100011                                           加上0X10000(unicode)
128035                                                         (10进制)
1F423                                                          (16进制）
     000          011111          010000          100011       因为在U+10000到U+1FFFFF之间，所以将二进制补成21个bit，前面补0,分成4组
11110xxx 	10xxxxxx 	10xxxxxx 	10xxxxxx       填补到对应的x位置
11110000 	10011111 	10010000 	10100011       转换成UTF-8的编码(UTF-8)
240             159             144             163            (10进制)
F0              9F              90              A3             (16进制）

F09F90A3
```
