# How to deploy IRISHUB monitor
Please make sure that iris is installed in your computer and added to \$PATH.You can see this page for insturcion https://github.com/irisnet/irishub. You also need /bin/bash, wc, ps to ensure the monitor work properly.
1. Download the monitoring tools
```shell
wget https://raw.githubusercontent.com/programokey/monitor/master/monitor.tar.gz
```
2. Uncompress the monitoring tools:
```
tar -xzvf monitor.tar.gz
```
3. Edit the running parameters
```shell
cd monitor
vim start.sh
```
edit the third command in start.sh
```
modify
-a=378E63271D5BE927443E17CBAAFE68DEFF383DA7
to 
-a=<hex encoded validator address>
```

```
modify
--chain-id=fuxi-test
to
--chain-id=<blockchain id that you want to monitor>
```

```
modify
--node="tcp://localhost:26657"
to
--node=<listening address of the node that you want to monitor ("tcp://localhost:26657" by default, you should not change this if you didn't modify your rpc port)>
```

4. start the monitoring tools
```
./start.sh
```
5. then, you can visit http://localhost:3000/ to see the grafana monitoring page. The default username and password are both admin. We strongly recommend that immediately change your username & password after login.
6. Click the Home Button, and open the IRIS HUB. Then you can see all the monitor term.
7. stop the monitor
```
./stop.sh
```
