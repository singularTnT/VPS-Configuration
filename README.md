# Set up a VPS with google BBR
主要介绍搭建虚拟专用服务器(VPS)，以及加入谷歌BBR优化算法实现TCP加速

（以下配置方法及流程均来源于网络，仅作整理，该方法仅用于学习和交流）
****
	
|Author|singularTnT|
|---|---
|E-mail|liuweiping1995@gmail.com


****

## 选择一个VPS
常用VPS如下所示

|服务器名 | 链接|
| :------------ |:---------------:|
|Vultr  | https://www.vultr.com/ |
|Linode  | https://www.linode.com/ |
|BandwagonHost  | EN: http://www.bandwagonhost.com/ <br>CN: http://banwagong.cn/ |
|DigitalOcean  | https://www.digitalocean.com/ |
|SugarHosts  | https://www.sugarhosts.com/zh-cn/ |
|...... | ...... |

#### VPS选择的几点注意事项
- [x] 价格
- [x] 稳定
- [x] 服务器位置
- [x] 性能配置

请自行去官网查看或者百度

## vps配置
以Vultr在Windows平台配置为例：

1. 下载安装putty客户端：<br>
http://www.putty.org/

2. 部署新的服务器<br>
	<1> 加号图标部署新的服务器<br>
![deploy new server](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/deploy_new_server.png)
	<2> server location选最近的<br>
![server location](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_location.png)
	<3> server type随意，centos较为稳定<br>
![server type](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_type.png)
	<4> server size按自己需求选(土豪请随意)，一般5刀的够4个人左右用了<br>
![server size](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_size.png)
	<5> 余下的不折腾的按默认就行，点击右下角蓝色框"Deploy Now"<br>
![deploy now](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_deploynow.png)

3. 登陆服务器<br>
	<1> 回到主界面，点击最左侧的“Servers”会显示你当前部署的服务器<br>
![server](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_tokyo_server.png)
	<2> 点击你所部署的服务器，会显示当前的“Server Information”，注意以下的“IP Address”和“Password”<br>
![server_info](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_ip_mm.png)
	<3> 登陆服务器，打开putty，在红框的位置输入上一步的“IP Address”，其余默认即可，点击右下角“Open”<br>
![putty](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/putty.png)
	<4> 在控制台界面输入<br>
	```
	login as: 输入`root`
	password: 输入之前部署服务器获得的Pasword(在putty命令行节目中，右键一下表示粘贴)，回车
	```
	<br>
![putty_login](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/putty_login.png)


