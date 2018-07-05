manageappsrv MeridConfig.xml  beibang 1000001021

查询该程序的位置


![程序位置](https://i.imgur.com/980bUwb.jpg)

发现该程序目前运行的主机分表为：\
20-152   
21-144   
22-212

查询三台服务器的主备情况

![](https://i.imgur.com/te1yEcn.jpg)
![](https://i.imgur.com/KowlXBQ.jpg)

修改主服务器的配置：
20-152    对应为20-115(同一台主机)
21-144    对应为21-151
22-212    阿里云服务器

用apps分别进入以下几个服务器\
>20-116-->20-115（也是152）\
21-215-->21-151\
22-212

```
cd /usr/local/007ka/manageappsrv_20/21/22\
vi MeridConfig.xml  #添加 1000001021
```

重启程序:
```
ps -ef |grep manageappsrv
kill pid  (已经有supervisor 关闭后悔自动启动)
22使用sup_run.sh restart 因为没有apps权限
```

