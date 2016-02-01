# Shell Tips

## 快速查找当前目录最大的五个文件

``` shell
find . -xdev -ls | sort -n -k 7 | tail -5
```
