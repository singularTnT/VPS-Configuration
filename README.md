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
	<1>加号图标部署新的服务器<br>
![deploy new server](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/deploy_new_server.png)
	<2>server location选最近的<br>
![server location](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_location.png)
	<3>server type随意，centos较为稳定
![server type](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_size.png)
	<4>server size按自己需求和土豪程度选，一般5刀的够4个人左右用了
![server size](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_size.png)
	<5>余下的不折腾的按默认就行，点击右下角蓝色框"Deploy Now"
![deploy now](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_deploynow.png)

