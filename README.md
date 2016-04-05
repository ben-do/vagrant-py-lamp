# vagrant-py-lamp
A vagarnt box made up of python and LAMP 

# Pre-install 事前準備
1. 安裝Virtualbox
2. 安裝Vagrant

# Install 安裝
```
// 製作一個資料夾
$ mkdir py-lamp
$ cd py-lamp

// 下載box
$ vagrant box add py-lamp https://www.dropbox.com/s/phh35ne28x75kdv/py-lamp.box?dl=1
$ vagrant init py-lamp

// 啟動
$ vagrant up
```
# List 軟體清單
* ubuntu: 14.04
* apache2
* mysql: 5.5
* php: 5.5.9
* python 2.7
* pip
* virtualenv
* phpMyAdmin

# Account / Password
mysql:
`root` / `ubuntu`

# 使用phpMyAdmin
編輯Vagrantfile，加入port的轉送

```
config.vm.network "forwarded_port", guest: 80, host: 8080
```

重新啟動vagrant

```
vagrant provisioin
vagrant halt
vagrant up
```

在瀏覽器輸入`http://localhost:8080/phpmyadmin`即可連入資料庫
