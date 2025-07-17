漏洞一 开放重定向漏洞

路由地址： /zhaoshang/list.php

找到可控变量 $_SERVER
 ![img](images1/图片1.png)

这段代码用于删除名为“zzcmscpid”的cookie后，通过JavaScript跳转到请求的来源页（Referer），但未对Referer进行任何验证。

验证漏洞

首先访问该页面

http://zz.cms/zhaoshang/list.php
 ![img](images1/图片2.png)

 

尝试构造Referer

  ![img](images1/图片3.png)

  ![img](images1/图片4.png)

发放数据包，发现页面跳转，dnslog有回显数据

  ![img](images1/图片5.png)
   ![img](images1/图片6.png)
