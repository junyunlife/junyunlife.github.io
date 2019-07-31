---
layout: wiki
title: Tomcat 远程调试
categories: Java
description: 远程调试tomcat的代码。
keywords: JAVA, Tomcat
---



# Tomcat 远程调试

## 使用场景: 微信小程序 等 本地环境很难绕过权限测试的时候。


## 一、 Tomcat 配置

1） : 编辑  bin 目录下 catalina.sh 如果是 windos 系统 请编辑catalina.bat 。

首先找到 文件中JPDA_ADDRESS 。 ip地址要改成本地局域网IP。端口随意改成一个可用的。



![image-20190720112233501](http://r.photo.store.qq.com/psb?/V13ICkPX2f64gY/E7TNe*IjJTwwXB8ZKZ6x6tRTrrb1T5L6GWiucWHy580!/r/dLYAAAAAAAAA)

2）：关闭tomcat (如果已经启动的话)

3)  ： 启动tomcat （关键）

启动tomcat的时候不能再用./startup.sh 这个命令了。而是用下面的

```shell
./catalina.sh jpda start 
```

4):如果启动成功tomcat 配置就完成了



## 二、 IDEA 配置

1） 添加 启动选项

![image-20190720112833299](http://r.photo.store.qq.com/psb?/V13ICkPX2f64gY/4S8fDF*5XyLIXyA1MQSNoWElRdqAMX3xQW.XpB6tNfs!/r/dLsAAAAAAAAA)



2）选择远程 也就是Remote

![image-20190720112920021](http://r.photo.store.qq.com/psb?/V13ICkPX2f64gY/RZ1SPQgiyS.FgmGmYU*kKn97icS.HjeNZDkEx3rkmBY!/r/dFMBAAAAAAAA)



3） 配置 tomcat 所在机器的IP  和 端口   然后选择需要调试的模块。设置完这些之后IDEA的 配置就弄好了

Host:  tomcat 。所在机器的IP

Port: 访问端口。 

Use module class path。 需要调试的代码模块

![image-20190720113123348](http://r.photo.store.qq.com/psb?/V13ICkPX2f64gY/DIROlpXTSMDPAXUWtE06DEKjL83Tyw.Fuor7.THZoGc!/r/dFMBAAAAAAAA)



4） 启动 IDEA

![image-20190720113359347](http://r.photo.store.qq.com/psb?/V13ICkPX2f64gY/D3vrb.HZ1anOuSamXmik8EEXf74KBCjN7rtMUKBqOuM!/r/dAYBAAAAAAAA)





