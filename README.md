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

#### 1. 下载安装putty客户端：<br>
http://www.putty.org/

#### 2. 部署新的服务器<br>
<1> 点击加号部署新的服务器<br>
![deploy new server](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/deploy_new_server.png)<br>
<2> server location选最近的<br>
![server location](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_location.png)<br>
<3> server type随意，CentOS较为稳定<br>
![server type](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_type.png)<br>
<4> server size按自己需求选(土豪请随意)，一般5刀的够4台左右设备用了<br>
![server size](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_size.png)<br>
<5> 余下的不折腾的按默认就行，点击右下角蓝色框"Deploy Now"<br>
![deploy now](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_deploynow.png)<br>

#### 3. 登陆服务器<br>
<1> 回到主界面，点击最左侧的“Servers”会显示你当前部署的服务器<br>
![server](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_tokyo_server.png)<br>
<2> 点击你所部署的服务器，会显示当前的“Server Information”，注意以下的“IP Address”和“Password”<br>
![server_info](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/vultr_server_ip_mm.png)<br>
<3> 登陆服务器，打开putty，在红框的位置输入上一步的“IP Address”，其余默认即可，点击右下角“Open”<br>
![putty](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/putty.png)<br>
<4> 在控制台界面输入<br>
```
login as: 输入"root"
password: 输入之前部署服务器获得的Pasword(在putty命令行界面中，右键一下表示粘贴)，回车
```
![putty_login](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/putty_login.png)<br>

#### 4. 配置服务器端<br>
<1> 在命令行界面顺序输入以下三行命令<br>
```
wget --no-check-certificate -O shadowsocks-go.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-go.sh

chmod +x shadowsocks-go.sh

./shadowsocks-go.sh 2>&1 | tee shadowsocks-go.log
```
<2> 脚本出现以下界面，提示设置服务器端ss密码<br>
![putty_1](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/putty_c_1.png)<br>
<3> 提示设置服务端口，默认回车即可<br>
![putty_2](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/putty_c_2.png)<br>
<4> 提示设置加密方式，任意加密方式即可(考虑到不同设备端支持的加密格式不同，选默认aes-256-cfb，如移动设备不支持可更换)<br>
![putty_3](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/putty_c_3.png)<br>
<5> 等待脚本自动配置，提示配置完成，并且出现以下ss信息界面，记住以下红色框信息<br>
![putty_4](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/putty_c_4.png)<br>

#### 5. 配置本地Shadowsocks<br>
<1> 下载ss客户端 https://github.com/shadowsocks/shadowsocks-windows/releases<br>
<2> 打开ss客户端，如下图输入之前红色框中对应的信息，点击确认，并且在windows界面右下角图标右键，勾选“启动系统代理”选项<br>
![ss](https://github.com/singularTnT/VPS-Configuration/blob/master/pic/ss.png)<br>
<3> 然后找几个不存在的网站测试XD<br>

## (Optional)服务器端配置BBR算法
服务器端加入谷歌BBR优化算法可以实现TCP加速，可流畅观看油管的4K资源，关于BBR算法，请转到https://github.com/google/bbr 并且参考相关文献<br>

在之前的命令行界面输入以下命令即可<br>
```
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && ./bbr.sh
```
接下来去油管试试或者Ping一下延迟或找个下载工具自行测试<br>

## (Optional)Ubuntu配置本地Shadowsocks<br>
未完待续

## 声明
以上内容绝大部分均参考于大神“秋水逸冰”，如细节有不明白处请转至“秋水逸冰”提供的教程https://teddysun.com/
侵删
