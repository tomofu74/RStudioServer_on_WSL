# RStudioServer_on_WSL

How to install RStudio server on WSL (Windows Subsystem for Linux)

1. WSL のセットアップ
2. Microsoft StoreからLinuxをインストール<br>
詳細参考：　http://www.atmarkit.co.jp/ait/articles/1608/08/news039.html

3. WSLにログインして、 環境の整備。
$ sudo apt update
$ sudo apt upgrade
（念のため、WSLを再起動（いったん終了して再度立ち上げる）

4. WSL上で、RstudioServerをセットアップ
$ sudo apt install r-base
$ sudo apt-get install gdebi-core
$ wget https://download2.rstudio.org/rstudio-server-1.1.463-amd64.deb
$ sudo gdebi rstudio-server-1.1.463-amd64.deb
参考：　https://www.rstudio.com/products/rstudio/download-server/