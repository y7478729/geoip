# 一、 文件说明
## 1. 规则集文件类型
① [Clash](https://github.com/Dreamacro/clash) GeoX 规则集文件，包括：Country.mmdb、geoip.dat 和 geoip.metadb（仅限 [Clash.Meta 内核](https://github.com/MetaCubeX/mihomo)）等  
② [sing-box](https://github.com/SagerNet/sing-box) GeoX 规则集文件，包括：geoip.db 等
## 2. 数据源
① 每天凌晨 2 点半（北京时间）自动构建，根据 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) 进行深度定制，可点击查看包含的 [IP 段列表](https://github.com/DustinWin/geoip/tree/master/IPs)  
② `geoip,netflix,🎥 奈飞视频` 源采用 [blackmatrix7/ios_rule_script/Netflix/Netflix_IP.txt](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Netflix)  
③ `geoip,telegram,📲 电报消息` 源采用 [Telegram IP 段](https://core.telegram.org/resources/cidr.txt)  
④ `geoip,private,🔒 私有网络` 源采用 [blackmatrix7/ios_rule_script/Lan](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Lan)  
⑤ `geoip,cn,🇨🇳 国内 IP` 源采用 [GeoLite2/cn.txt](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data)、[17mon/china_ip_list](https://github.com/17mon/china_ip_list)、[gaoyifan/china-operator-ip](https://github.com/gaoyifan/china-operator-ip) 和 [blackmatrix7/ios_rule_script/ChinaIPs/ChinaIPs_IP.txt](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaIPs) 组合

**规则名称与规则集文件的对应关系如下表：**
|文件名称|包含规则|
|-----|-----|
|Country-all.mmdb、geoip-all.dat、geoip-all.metadb 和 geoip-all.db|来源于 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip)，[点此查看](https://github.com/Loyalsoldier/geoip/tree/release/text)|
|Country.mmdb、geoip.dat、geoip.metadb 和 geoip.db|`netflix`、`telegram`、`private` 和 `cn`|
|Country-lite.mmdb、geoip-lite.dat、geoip-lite.metadb 和 geoip-lite.db|~~`netflix`~~、`telegram`、`private` 和 `cn`|
# 二、 文件下载（以 Country.mmdb、geoip.dat、geoip.metadb 和 geoip.db 为例）
<table>
  <tr>
    <td rowspan="3">Country.mmdb</td>
    <td>GitHub 源：https://raw.githubusercontent.com/DustinWin/geoip/clash/Country.mmdb</td>
  </tr>
  <tr>
    <td>jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/Country.mmdb</td>
  </tr>
  <tr>
    <td>GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/geoip/clash/Country.mmdb</td>
  </tr>
  <tr>
    <td rowspan="3">geoip.dat</td>
    <td>GitHub 源：https://raw.githubusercontent.com/DustinWin/geoip/clash/geoip.dat</td>
  </tr>
  <tr>
    <td>jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/geoip.dat</td>
  </tr>
  <tr>
    <td>GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/geoip/clash/geoip.dat</td>
  </tr>
  <tr>
    <td rowspan="3">geoip.metadb</td>
    <td>GitHub 源：https://raw.githubusercontent.com/DustinWin/geoip/clash/geoip.metadb</td>
  </tr>
  <tr>
    <td>jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/geoip.metadb</td>
  </tr>
  <tr>
    <td>GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/geoip/clash/geoip.metadb</td>
  </tr>
  <tr>
    <td rowspan="3">geoip.db</td>
    <td>GitHub 源：https://raw.githubusercontent.com/DustinWin/geoip/sing-box/geoip.db</td>
  </tr>
  <tr>
    <td>jsDelivr 源：https://cdn.jsdelivr.net/gh/DustinWin/geoip@sing-box/geoip.db</td>
  </tr>
  <tr>
    <td>GitHub Proxy 源：https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/geoip/sing-box/geoip.db</td>
  </tr>
</table>

# 三、 文件导入
① 导入到 Linux 端（以 [ShellClash](https://github.com/juewuy/ShellCrash) 导入 Country.mmdb、geoip.dat、geoip.metadb 和 geoip.db 为例）  
连接 SSH 后执行如下命令：
```
# Clash 内核
curl -o $CRASHDIR/Country.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/Country.mmdb
curl -o $CRASHDIR/geoip.dat -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/geoip.dat
# Clash.Meta 内核
curl -o $CRASHDIR/geoip.metadb -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/geoip.metadb
# sing-box 内核
curl -o $CRASHDIR/geoip.db -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@sing-box/geoip.db
$CRASHDIR/start.sh restart
```
② 导入到 Windows 端（以 [Clash Verge](https://github.com/MetaCubeX/clash-verge) 导入 geosite.dat、Country.mmdb、geoip.dat 和 geoip.metadb 为例）  
以管理员身份运行 CMD，执行如下命令：
```
taskkill /f /t /im "Clash Verge*"
taskkill /f /t /im Clash-Verge*
taskkill /f /t /im clash-meta*
curl -o %APPDATA%\io.github.clash-verge-rev.clash-verge-rev\Country.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/Country.mmdb
curl -o %APPDATA%\io.github.clash-verge-rev.clash-verge-rev\geoip.dat -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/geoip.dat
curl -o %APPDATA%\io.github.clash-verge-rev.clash-verge-rev\geoip.metadb -L https://cdn.jsdelivr.net/gh/DustinWin/geoip@clash/geoip.metadb
pause
```
