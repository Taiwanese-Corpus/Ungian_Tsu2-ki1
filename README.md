# 楊允言老師的主機映像檔
* 楊允言老師提供的檔案，經由打包成`ova`映像檔，歡迎大家使用
* `ova`可以用`VirtualBox`、`VMware`開啟（僅使用Mint 17的`Virtualbox`試驗）
* 使用者密碼攏是`tai5gi2`
* 登入一個使用者，開瀏覽器，輸入`localhost`就看會著網頁

## ip093
* 原網址：<http://ip194093.ntcu.edu.tw>
* Fedora 13 64bit
* apache2對應的資料在`/home/apache/html`
* ova映像檔[下載](https://www.dropbox.com/s/b6hkh0zb1z8m8mf/ip093.ova?dl=0)，約68GB。VM解開後約136GB。

## taibun
* 原網址：<http://www.taibun.tw>
* Ubuntu 11.04 64bit
* apache2對應的資料在`/opt/www.taibun.tw`，設定檔在`/opt/apache-tomcat-5.5.33`
* ova映像檔[下載](https://www.dropbox.com/s/cakqbm6b3hedhic/taibun.ova?dl=0)，約63GB。VM解開後約224GB。

## 裝vm
### ip093
```
wget -O ip093.ova https://www.dropbox.com/s/b6hkh0zb1z8m8mf/ip093.ova?dl=0
vboxmanage import ip093.ova
vboxmanage modifyvm "ip093" --natpf1 "http,tcp,,8000,,80"
vboxmanage startvm ip093 --type headless
```
### taibun
```
wget -O taibun.ova https://www.dropbox.com/s/cakqbm6b3hedhic/taibun.ova?dl=0
vboxmanage import taibun.ova
vboxmanage modifyvm jsp --name taibun
vboxmanage modifyvm taibun --natpf1 "http,tcp,,8000,,80"
vboxmanage startvm taibun --type headless
```
