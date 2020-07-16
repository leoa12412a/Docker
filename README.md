# Docker

在程式開發的過程中，常常會發生環境不同或是系統設定有誤的情況，這樣的情況如果在本機重現不了 bug 真的很讓人頭痛，如果有一種技術可以讓我們本機的環境跟測試站、正式站一樣或是只要更接近一點，一定可以省下不少時間。於是 Docker 出現了，Docker 是現在當紅的虛擬化技術，它非常的輕量，啟動、停止是可以在幾秒內完成的那種，同時 Docker 對系統資源需求很少，甚至一台主機可以同時啟動數百甚至數千個 Docker 容器。為了要學習和體驗一下 Docker 的威力，所以我試著用 Docker 來部署我的 Rails 應用程式，這是個很好的機會讓我對不管是 Docker 技術還是環境部署都有更深一層的認識！

* 懶人包 : Docker可以幫你減少設定環境可能會出錯的現象。

## Centos install docker

1.在安裝 Docker 前先更新一下 YUM Repository:
```
yum -y update
```

2.更新 YUM Repository 後可以安裝 Docker 及其相關套件:
```
yum -y install docker docker-registry
```

3.安裝好 Docker 後, 啟動 Docker 及設定 Docker 開機自動啟動:
```
systemctl enable docker
systemctl start docker
```

4.要檢查 Docker 是否正確啟動, 可用 status 選項:
```
systemctl status docker.service
```

5.一切沒有問題的話, 可以嘗試下載 Docker 的映像檔, 例如下載 centos 的映像檔
```
docker pull centos
```

6.然後可以執行 Docker Container, 以上面下載的 centos 映像檔為例, 指令是:
```
docker run -i -t centos /bin/bash
```

這樣就完成了, 現在已經在 Docker 的 centos Container 內使用 /bin/bash.

要離開 Container, 只要在指令模式按組合鍵 Ctrl-p + Ctrl-q.



# Docker-compose

```
參考:https://docs.docker.com/compose/install/

sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose -v
```

<strike>
## Install docker-compose

安裝所需的packages
```
$ sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

配置docker-ce repo(路徑來源)
```
$ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

安裝Enterprise Linux的額外軟件包
```
$ sudo yum install epel-release
```

安裝python-pip
```
$ sudo yum install -y python-pip
```

安裝Docker Compose
```
$ sudo pip install docker-compose
```
</strike>
