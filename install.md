# 本腳本適用環境
系統支持：CentOS 6+，Debian 7+，Ubuntu 12+  
內存要求：≥128M

# 關於本腳本
1. 一鍵安裝 Shadowsocks-Python， ShadowsocksR， Shadowsocks-Go， Shadowsocks-libev 版（四選一）服務端；
2. 各版本的啟動腳本及配置文件名不再重合；
3. 每次運行可安裝一種版本；
4. 支持以多次運行來安裝多個版本，且各個版本可以共存（注意端口號需設成不同）；
5. 若已安裝多個版本，則卸載時也需多次運行（每次卸載一種）；

# 默認配置
服務器端口：自己設定（如不設定，默認從 9000-19999 之間隨機生成）  
密碼：自己設定（如不設定，默認為 teddysun.com）  
加密方式：自己設定（如不設定，Python 和 libev 版默認為 aes-256-gcm，R 和 Go 版默認為 aes-256-cfb）  
協議（protocol）：自己設定（如不設定，默認為 origin）（僅限 ShadowsocksR 版）  
混淆（obfs）：自己設定（如不設定，默認為 plain）（僅限 ShadowsocksR 版）  
備註：腳本默認創建單用戶配置文件，如需配置多用戶，請手動修改相應的配置文件後重啟即可。  

# 客戶端下載
常規版 Windows 客戶端  
https://github.com/shadowsocks/shadowsocks-windows/releases  
  
ShadowsocksR 版 Windows 客戶端  
https://github.com/shadowsocksrr/shadowsocksr-csharp/releases  
  
# 使用方法
使用root用戶登錄，依次運行以下命令：
```bash
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```

安裝完成後，腳本提示如下  

```bash
Congratulations, your_shadowsocks_version install completed!
Your Server IP        :your_server_ip
Your Server Port      :your_server_port
Your Password         :your_password
Your Encryption Method:your_encryption_method

Your QR Code: (For Shadowsocks Windows, OSX, Android and iOS clients)
 ss://your_encryption_method:your_password@your_server_ip:your_server_port
Your QR Code has been saved as a PNG file path:
 your_path.png

Welcome to visit:https://teddysun.com/486.html
Enjoy it!

```

# 卸載方法
若已安裝多個版本，則卸載時也需多次運行（每次卸載一種）  
使用root用戶登錄，運行以下命令：  
```bash
./shadowsocks-all.sh uninstall
```

# 啟動腳本
啟動腳本後面的參數含義，從左至右依次為：啟動，停止，重啟，查看狀態。  
  
Shadowsocks-Python 版：  
/etc/init.d/shadowsocks-python start | stop | restart | status  
  
ShadowsocksR 版：  
/etc/init.d/shadowsocks-r start | stop | restart | status  
  
Shadowsocks-Go 版：  
/etc/init.d/shadowsocks-go start | stop | restart | status  
  
Shadowsocks-libev 版：  
/etc/init.d/shadowsocks-libev start | stop | restart | status  
  
# 各版本默認配置文件
Shadowsocks-Python 版：  
/etc/shadowsocks-python/config.json  
  
ShadowsocksR 版：  
/etc/shadowsocks-r/config.json  
  
Shadowsocks-Go 版：  
/etc/shadowsocks-go/config.json  
  
Shadowsocks-libev 版：  
/etc/shadowsocks-libev/config.json  
  
  
  
# BBR plus
```bash
wget "https://github.com/chiakge/Linux-NetSpeed/raw/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh 
```
 

# BBR

使用BBR加速器  
讓訪問速度加速，飛起來！使用 BBR 加速工具。  

## 安裝 BBR
```
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
```
## 獲取讀寫權限
```
chmod +x bbr.sh
```
## 啟動BBR安裝
```
./bbr.sh
```
接著按任意鍵，開始安裝，坐等一會。安裝完成一會之後它會提示我們是否重新啟動vps，我們輸入 y 確定重啟服務器。  
  
重新啟動之後，輸入 lsmod | grep bbr 如果看到 tcp_bbr 就說明 BBR 已經啟動了。  
  
再訪問一下 Youtube，1080p 超高清，很順暢不卡頓！  
