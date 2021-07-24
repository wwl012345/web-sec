# SSH 端口转发和sock5代理

## SSH 端口转发

### 本地转发
本地访问 127.0.0.1:8888 转发到 1.1.1.1:80    
```
ssh -CfNg -L 80:127.0.0.1:8888 user@1.1.1.1
```
### 远程转发

远程访问 1.1.1.1:80 转发到 127.0.0.1:8888   
```
ssh -CfNg -R 80:127.0.0.1:8888 user@1.1.1.1
```

## SSH sock5代理

在在1.1.1.1开启sock5服务，映射到本地 0.0.0.0:1080
```
ssh -qTfnN -D 0.0.0.0:1080 root@1.1.1.1
```