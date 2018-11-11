# RStudioServer_on_WSL

＜以下、失敗の記録。最終的にうまくいかない、そのうえ、ROpenのパフォーマンスが悪い＞

How to install RStudio server on WSL (Windows Subsystem for Linux)

1. WSL のセットアップ
2. Microsoft StoreからLinuxをインストール
詳細参考：　http://www.atmarkit.co.jp/ait/articles/1608/08/news039.html

3. WSLにログインして、 環境の整備。
$ sudo apt update
$ sudo apt upgrade
（念のため、WSLを再起動（いったん終了して再度立ち上げる）

4. INTEL MKL をセットアップ。
$ wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
$ sudo apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
$ sudo wget https://apt.repos.intel.com/setup/intelproducts.list -O /etc/apt/sources.list.d/intelproducts.list 
$ sudo apt-get update
（参考）　https://qiita.com/ymzkd/items/55a9c936df60394572fc

$ sudo apt-get install intel-mkl-2018.3-051


4. WSL上で、Rをセットアップ
$ sudo apt install r-base

4.1. Microsoft R Open with MKL で上書き
$ wget https://mran.blob.core.windows.net/install/mro/3.5.1/microsoft-r-open-3.5.1.tar.gz
$ tar -zxf microsoft-r-open-3.5.1.tar.gz

$ sudo apt-get install gdebi-core
$ wget https://download2.rstudio.org/rstudio-server-1.1.463-amd64.deb
$ sudo gdebi rstudio-server-1.1.463-amd64.deb
参考：　https://www.rstudio.com/products/rstudio/download-server/

