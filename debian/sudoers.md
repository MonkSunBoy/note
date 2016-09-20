# sudoers

## 修改sudo的环境变量

在/etc/sudoers中添加一下内容：

```
Defaults  env_keep += "GOROOT"
Defaults  env_keep += "GOPATH"
```
