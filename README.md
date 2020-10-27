# RaspberryPi-RPiMonitor

## Install RPi-Monitor

apt-get 預設不支援https，因此需要安裝 RPi-Monitor 的公鑰來信任 RPi-Monitor 的儲存庫。
```
pi@raspberrypi:~ $ sudo apt-get install dirmngr
```
```
pi@raspberrypi:~ $ sudo apt-key adv --recv-keys --keyserver keyserver.ubuntu.com 2C0D3C0F
```

<br>

新增 RPi-Monitor 至儲存庫清單。
```
pi@raspberrypi:~ $ sudo wget http://goo.gl/vewCLL -O /etc/apt/sources.list.d/rpimonitor.list
```
<br>

進行安裝。
```
pi@raspberrypi:~ $ sudo apt-get update
```
```
pi@raspberrypi:~ $ sudo apt-get install rpimonitor
```

## Usage

<b>連線: <u>http://IP:8888</u></b>

Status

<img src="img/RPi-Monitor Status.png">

Statistics

<img src="img/RPi-Monitor Statistics.png">

<br>

執行更新
```
pi@raspberrypi:~ $ sudo /etc/init.d/rpimonitor update
```

<br>

若要啟動其它監控項目，可至設定檔修改。
```
pi@raspberrypi:~ $ sudo nano /etc/rpimonitor/data.conf
```

<br>

將要顯示設備的監控項目 include 進去。

例如: 顯示 WiFi 結果(可刪除 include 前的 # 號): 
```
include=/etc/rpimonitor/template/wlan.conf
```

<br>

重新啟動 RPi-Monitor
```
pi@raspberrypi:~ $ sudo service rpimonitor restart
```

<br>

停止 RPi-Monitor
```
pi@raspberrypi:~ $ sudo service rpimonitor stop
```

<br>

> 參考資料: [RPi-Monitor](https://github.com/XavierBerger/RPi-Monitor)

> 參考資料: [樹莓派的監控系統 RPi-Monitor](https://atceiling.blogspot.com/2019/04/raspberry-pi-47-rpi-monitor.html)
