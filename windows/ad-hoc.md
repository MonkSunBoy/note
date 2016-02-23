# 建立ad-hoc网络

* 以管理员身份打开命令行工具

* 查看是否支持
```
netsh wlan show drivers
```

* 设置网络
```
netsh wlan set hostednetwork mode=allow ssid=<enter_network_name_here> key=<enter_password_here>
```

* 开启网络
```
netsh wlan start hostednetwork
```
