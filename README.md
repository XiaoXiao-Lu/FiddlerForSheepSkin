# FiddlerForSheepSkin
##### ios端羊了个羊通关获取皮肤，Fiddler

1. 首先去  https://www.cnblogs.com/mini-monkey/p/11286264.html  看教程把Fiddler安装配置好。

2. 访问该链接 https://www.aliyundrive.com/s/fdXrJzQsivQ 下载旧版的3.6.0微信覆盖原来的微信，因为新版的Fiddler可能抓包不了

3. 打开Fiddler

   ![image-20220918020822678](img/image-20220918020822678.png)

然后打开微信，打开羊了个羊小程序，进入主界面。然后返回Fiddler界面，看看有没有箭头所标注的数据

![image-20220918021024878](img/image-20220918021024878.png)

若没有，则说明没有抓到羊了个羊的包，然后去https://blog.csdn.net/weixin_46552558/article/details/124037807 按照步骤操作，微信重启后打开羊了个羊，回到Fiddler发现就能抓到上图中的包了。



4.接着手机电脑连接同一网络，使手机和电脑在同一个局域网环境下。电脑win+R 输入cmd ，在黑框里输入ipconfig查看电脑ip地址

![image-20220918021838491](img/image-20220918021838491.png)



然后打开iphone，找到连接的WiFi，点旁边的i图标，点击配置代理，选择手动，服务器填入电脑的ip端口8888，然后保存。接着打开浏览器输入 你的电脑ip:88888   例如 192.1.1.1:8888 ,跳转到页面后，点击最后一行的蓝字，然后安装描述文件，开启证书。



5.打开Fiddler，点击这个

![image-20220918022250937](img/image-20220918022250937.png)



找到这一行![image-20220918022319712](img/image-20220918022319712-1663439734915.png)

在最后的if下面添加这一句代码

![image-20220918022353125](img/image-20220918022353125.png)

~~~java
 if (oSession.PathAndQuery=="/sheep/v1/game/map_info_new?map_id=90018") {
            oSession.PathAndQuery="/sheep/v1/game/map_info_new?map_id=80001";
   }

~~~

点击左上角保存。

最后手机打开羊了个羊，开始游戏，发现第二关和第一关一样了！
