# 一、 文件说明
## 1. 规则集文件类型
① [Clash](https://github.com/Dreamacro/clash) GeoX 规则集文件，包括：Country.mmdb、geoip.dat 和 geoip.metadb（仅限 [Clash.Meta 内核](https://github.com/MetaCubeX/mihomo)）等  
② [sing-box](https://github.com/SagerNet/sing-box) GeoX 规则集文件，包括：geoip.db 等
## 2. 数据源
① 每天凌晨 2 点半（北京时间）自动构建，根据 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) 进行深度定制  
② `geoip:netflix` 源采用 [blackmatrix7/ios_rule_script/Netflix/Netflix_IP.txt](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Netflix)  
③ `geoip:telegram` 源采用 [Telegram IP](https://core.telegram.org/resources/cidr.txt)  
④ `geoip:private` 源采用 [blackmatrix7/ios_rule_script/Lan](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Lan)（IP 部分）  
⑤ `geoip:cn` 源采用 [GeoLite2/cn.txt](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data)、[17mon/china_ip_list](https://github.com/17mon/china_ip_list)、[gaoyifan/china-operator-ip](https://github.com/gaoyifan/china-operator-ip) 和 [blackmatrix7/ios_rule_script/ChinaIPs/ChinaIPs_IP.txt](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaIPs) 组合  
**规则名称与规则集文件的对应关系如下表：**
|文件名称|包含规则|
|-----|-----|
|Country-all.mmdb、geoip-all.dat、geoip-all.metadb 和 geoip-all.db|来源于 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip)，[点此查看](https://github.com/Loyalsoldier/geoip/tree/release/text)|
|Country.mmdb、geoip.dat、geoip.metadb 和 geoip.db|`netflix`、`telegram`、`private` 和 `cn`|
|Country-lite.mmdb、geoip-lite.dat、geoip-lite.metadb 和 geoip-lite.db|`telegram`、`private` 和 `cn`|
# 二、 文件下载（以 Country.mmdb、geoip.dat、geoip.metadb 和 geoip.db 为例）
## 1. Country.mmdb
① GitHub 源：https://raw.githubusercontent.com/DustinWin/geoip/clash/Country.mmdb  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/Country.mmdb  
③ GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/geoip/clash/Country.mmdb
## 2. geoip.dat
① GitHub 源：https://raw.githubusercontent.com/DustinWin/geoip/clash/geoip.dat  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/geoip.dat  
③ GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/geoip/clash/geoip.dat
## 3. geoip.metadb
① GitHub 源：https://raw.githubusercontent.com/DustinWin/geoip/clash/geoip.metadb  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/geoip.metadb  
③ GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/geoip/clash/geoip.metadb
## 4. geoip.db
① GitHub 源：https://raw.githubusercontent.com/DustinWin/geoip/sing-box/geoip.db  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/geoip@sing-box/geoip.db  
③ GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/geoip/sing-box/geoip.db
# 三、 文件导入（以 [ShellClash](https://github.com/juewuy/ShellCrash) 导入 Country.mmdb、geoip.dat、geoip.metadb 和 geoip.db 为例）
连接 SSH 后执行如下命令：
```
curl -o $CRASHDIR/Country.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/Country.mmdb
curl -o $CRASHDIR/geoip.dat -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/geoip.dat
curl -o $CRASHDIR/geoip.metadb -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/geoip.metadb
curl -o $CRASHDIR/geoip.db -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@sing-box/geoip.db
$CRASHDIR/start.sh restart
```
