# VPS配置
The procedure of setting up a vps server with google BBR algorithm
主要介绍搭建虚拟专用服务器(vps)，以及加入谷歌BBR优化算法实现TCP加速

（以下配置方法及流程均来源于网络，仅作整理，该方法仅用于学习和交流）
****
	
|Author|singularTnT|
|---|---
|E-mail|liuweiping1995@gmail.com


****
## 选择一个VPS
常用vps包括
Vultr：https://www.vultr.com/
Linode：https://www.linode.com/
BandwagonHost：http://www.bandwagonhost.com/ // http://banwagong.cn/
DigitalOcean：https://www.digitalocean.com/
SugarHosts：https://www.sugarhosts.com/zh-cn/
......
vps选择的几点注意事项：
<1>价格 <2>稳定性 <3>服务器位置 <4>性能配置
请自行去官网查看或者百度

## vps配置
以下以Vultr在Windows平台配置过程为例：

1. 下载安装putty客户端：http://www.putty.org/
2.
