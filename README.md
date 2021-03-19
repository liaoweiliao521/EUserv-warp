## EUserv IPV6添加WARP IPV4

### 脚本仅针对OpenVZ、LXC架构的IPV6 only VPS，添加WARP IPV4网络支持，默认已设置IPV4优先

### 已测试通过Debian 10、Ubuntu 20.04，由于ProxySU，mack-a，phlinhng三大IPV6 Xray脚本对Centos并不友好，容易报错，故不做支持Centos系统的脚本了！
mack-a：https://github.com/mack-a/v2ray-agent

phlinhng：https://github.com/phlinhng/v2ray-tcp-tls-web

ProxySU：https://github.com/proxysu/ProxySU

### 详细视频教程及探讨：https://youtu.be/78dZgYFS-Qo

------------------------------------------------------------------------------------
## 主要步骤如下

### 一、登陆SSH（PC WIN系统）

开启IPV6网络方法：

方法1、电脑本地隧道  https://youtu.be/MPAP1jabQgE

方法2、IPV4跳板机   https://youtu.be/1Gq25zIEsRY

方法3、嘿呦终端      最小白的方法，自行google

有IPV6地址的直接登陆！

### 二、配置DNS64（仅从Github拉取安装脚本数据用，后续会被脚本内设置的公共DNS IPV6地址所取代，这样后续解析效果会更好）
echo -e "nameserver 2001:67c:2b0::4\nnameserver 2001:67c:2b0::6" > /etc/resolv.conf


### 三、整合Debian 10与Ubuntu 20.04，一键到底！


#### Debian 10/Ubuntu 20.04系统脚本
```
wget https://raw.githubusercontent.com/YG-tsj/EUserv-addv4-warp/main/ub20db10.sh && chmod +x ub20db10.sh && ./ub20db10.sh
```

#### 由于默认设置IPV4优先，可能你有时不希望IPV4优先（比如有些脚本申请证书识别报错），那么可以先关，再开（虽然重启后自动会开）

手动关闭WARP网络接口
```
wg-quick down wgcf
```

手动开启WARP网络接口 
```
wg-quick up wgcf
```



### 感谢P3terx大及原创者们，参考来源：
https://p3terx.com/archives/debian-linux-vps-server-wireguard-installation-tutorial.html

https://p3terx.com/archives/use-cloudflare-warp-to-add-extra-ipv4-or-ipv6-network-support-to-vps-servers-for-free.html

https://luotianyi.vc/5252.html
