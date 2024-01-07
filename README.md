# 一、 说明
- 注：深度定制的规则集可[点此](https://github.com/DustinWin/clash-geoip/tree/ips)查看包含的 IP 段列表
## 1. geoip-all.dat、Country-all.mmdb、geoip-all.metadb 和 geoip-all.db
① 源采用 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip)，包含如下分类（可[点此](https://github.com/Loyalsoldier/geoip/tree/release/text)查看其它国家或地区 IP 规则集）：
```
  - GEOIP,cloudflare,☁️ Cloudflare
  - GEOIP,cloudfront,🌐 CloudFront
  - GEOIP,facebook,👓 Facebook
  - GEOIP,fastly,🌎 Fastly
  - GEOIP,google,📢 谷歌
  - GEOIP,netflix,🎥 奈飞视频
  - GEOIP,telegram,📲 电报消息
  - GEOIP,twitter,✖️ Twitter
  - GEOIP,cn,🇨🇳 国内 IP
```
② .metadb 规则集文件适用于使用了 [Clash.Meta 内核](https://github.com/MetaCubeX/Clash.Meta)的客户端（下同）  
③ .db 规则集文件适用于使用了 [sing-box 平台](https://github.com/SagerNet/sing-box)的客户端（下同）
## 2. geoip.dat、Country.mmdb、geoip.metadb 和 geoip.db
① 根据 Loyalsoldier/geoip 进行深度定制，**有且仅有如下分类**：
```
  - GEOIP,netflix,🎥 奈飞视频
  - GEOIP,telegram,📲 电报消息
  - GEOIP,private,🔒 私有网络
  - GEOIP,cn,🇨🇳 国内 IP
```
② 每天早上 3 点（北京时间）自动构建   
③ `geoip:netflix` 源采用 [blackmatrix7/ios_rule_script/Netflix/Netflix_IP.txt](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Netflix)  
④ `geoip:telegram` 源采用 [Telegram IP](https://core.telegram.org/resources/cidr.txt)   
⑤ `geoip:private` 源采用 [blackmatrix7/ios_rule_script/Lan](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Lan)（IP 部分）  
⑥ `geoip:cn` 源采用 [GeoLite2/cn.txt](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data)、[17mon/china_ip_list](https://github.com/17mon/china_ip_list)、[gaoyifan/china-operator-ip](https://github.com/gaoyifan/china-operator-ip) 和 [blackmatrix7/ios_rule_script/ChinaIPs/ChinaIPs_IP.txt](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaIPs) 组合
## 3. geoip-lite.dat、Country-lite.mmdb、geoip-lite.metadb 和 geoip-lite.db
分别在 geoip.dat、Country.mmdb、geoip.metadb 和 geoip.db 的基础上去除了流媒体，**有且仅有如下分类**：
```
  - GEOIP,telegram,📲 电报消息
  - GEOIP,private,🔒 私有网络
  - GEOIP,cn,🇨🇳 国内 IP
```
# 二、 下载（以 geoip.dat、Country.mmdb、geoip.metadb 和 geoip.db 为例）
## 1. geoip.dat
① GitHub 源：https://github.com/DustinWin/clash-geoip/releases/download/latest/geoip.dat  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.dat  
③ GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/clash-geosite/release/geoip.dat
## 2. Country.mmdb
① GitHub 源：https://github.com/DustinWin/clash-geoip/releases/download/latest/Country.mmdb  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/Country.mmdb  
③ GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/clash-geosite/release/Country.mmdb
## 3. geoip.metadb
① GitHub 源：https://github.com/DustinWin/clash-geoip/releases/download/latest/geoip.metadb  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.metadb  
③ GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/clash-geosite/release/geoip.metadb
## 4. geoip.db
① GitHub 源：https://github.com/DustinWin/clash-geoip/releases/download/latest/geoip.db  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.db  
③ GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/clash-geosite/release/geoip.db
# 三、 导入（以 [ShellClash](https://github.com/juewuy/ShellCrash) 导入 geoip.dat 和 Country.mmdb 为例）
连接 SSH 后执行如下命令：
```
curl -o $CRASHDIR/GeoIP.dat -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.dat
curl -o $CRASHDIR/Country.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/Country.mmdb
$CRASHDIR/start.sh restart
```
