# 如何部署monitor
确保已经安装了iris等工具，系统中需要有/bin/bahs、wc、ps等命令。
1. 下载打包好的监控工具。
```shell
wget 。。。
```
2. 解压监控工具包:
```
tar -xzvf monitor.tar.gz
```
3. 修改运行参数
```shell
cd monitor
vim start.sh
```
将第三条命令中的:
```
-a=378E63271D5BE927443E17CBAAFE68DEFF383DA7
修改为
-a=<你的验证人地址的hex编码>
```

```
--chain-id=fuxi-test
修改为
--chain-id=<你要监控的网络的ID>
```

```
--node="tcp://localhost:26657"
修改为
--chain-id=<你要监控的节点监听的rpc端口(默认为26657)>
```

4. 启动监控工具
```
./start.sh
```
5. 接下来就可以在localhost:3000访问grafana监控。打开网页后使用默认用户名admin，默认密码admin登录。建议登录之后立即修改密码。
6. 点击Home按钮，然后在general中打开IRIS HUB即可看到监控项。
7. 关闭监控
```
./stop.sh
```

