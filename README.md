# 一、 说明
1. 根据 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) 进行深度定制，**有且仅有如下分类**：
```
  - GEOIP,cn,🇨🇳 国内 IP
  - GEOIP,lanip,🏠 私有网络
  - GEOIP,telegram,✈️ Telegram IP
```
2. 每天早上 3 点（北京时间）自动构建
3. `geoip:cn` 源采用 [blackmatrix7/ios_rule_script/ChinaMax](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaMax)（ChinaMax_IP.txt）
4. `geoip:lanip` 源采用 [blackmatrix7/ios_rule_script/Lan](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Lan)（IP 部分）
5. `geoip:telegram` 源采用 [Telegram IP](https://core.telegram.org/resources/cidr.txt)
# 二、 下载
## 1. geoip.dat
① GitHub 源：https://github.com/DustinWin/clash-geoip/releases/download/latest/geoip.dat  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.dat
## 2. Country.mmdb
① GitHub 源：https://github.com/DustinWin/clash-geoip/releases/download/latest/Country.mmdb  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/Country.mmdb
# 三、 导入 [ShellClash](https://github.com/juewuy/ShellClash)
连接 SSH 后执行如下命令：
```
curl -o $clashdir/GeoIP.dat -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/geoip.dat
curl -o $clashdir/Country.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/clash-geoip@release/Country.mmdb
$clashdir/start.sh restart
```
