# 一、 说明
- 注：[点此](https://github.com/DustinWin/clash-geoip/tree/ips)查看 IP 段列表
## 1. geoip.dat 和 Country.mmdb
① 根据 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) 进行深度定制，**有且仅有如下分类**：
```
  - GEOIP,netflix,🎥 Netflix
  - GEOIP,telegram,✈️ Telegram
  - GEOIP,private,🏠 私有网络
  - GEOIP,cn,🇨🇳 国内 IP
```
② 每天早上 3 点（北京时间）自动构建   
③ `geoip:netflix` 源采用 [blackmatrix7/ios_rule_script/Netflix/Netflix_IP.txt](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Netflix)  
④ `geoip:telegram` 源采用 [Telegram IP](https://core.telegram.org/resources/cidr.txt)   
⑤ `geoip:private` 源采用 [blackmatrix7/ios_rule_script/Lan](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Lan)（IP 部分）  
⑥ `geoip:cn` 源采用 [17mon/china_ip_list](https://github.com/17mon/china_ip_list)、[gaoyifan/china-operator-ip](https://github.com/gaoyifan/china-operator-ip) 和 [blackmatrix7/ios_rule_script/ChinaIPs/ChinaIPs_IP.txt](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaIPs) 组合
## 2. geoip-lite.dat 和 Country-lite.mmdb
分别在 geoip.dat 和 Country.mmdb 的基础上去除了流媒体，**有且仅有如下分类**：
```
  - GEOIP,telegram,✈️ Telegram
  - GEOIP,private,🏠 私有网络
  - GEOIP,cn,🇨🇳 国内 IP
```
# 二、 下载（以 geoip.dat 和 Country.mmdb 为例）
## 1. geoip.dat
① GitHub 源：https://github.com/DustinWin/clash-geoip/releases/download/latest/geoip.dat  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.dat
## 2. Country.mmdb
① GitHub 源：https://github.com/DustinWin/clash-geoip/releases/download/latest/Country.mmdb  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/Country.mmdb
# 三、 导入 [ShellClash](https://github.com/juewuy/ShellClash)（以 geoip.dat 和 Country.mmdb 为例）
连接 SSH 后执行如下命令：
```
curl -o $clashdir/GeoIP.dat -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.dat
curl -o $clashdir/Country.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/Country.mmdb
$clashdir/start.sh restart
```
