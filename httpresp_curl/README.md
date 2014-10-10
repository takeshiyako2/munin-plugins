# Munin plugin for http response time.


1) Copy plugin file to plugins directory.

```
# cp httpresp_curl_ /usr/share/munin/plugins/httpresp_curl_
# chmod 755 /usr/share/munin/plugins/httpresp_curl_
```


2) Make configure file.

```
# vim /etc/munin/plugin-conf.d/httpresp_curl 
```

```
[httpresp_curl_yahoo.co.jp]
  env.URL http://yahoo.co.jp/

[httpresp_curl_google.co.jp]
  env.URL http://google.co.jp/
```


3) Link plugin file.

```
# cd /etc/munin/plugins
# ln -s /usr/share/munin/plugins/httpresp_curl_ httpresp_curl_yahoo.co.jp
# ln -s /usr/share/munin/plugins/httpresp_curl_ httpresp_curl_google.co.jp
```

4) Run test.

```
# cd /etc/munin/plugins
# munin-run httpresp_curl_yahoo.co.jp
namelookup.value 0.021
connect.value 0.044
appconnect.value 0.000
pretransfer.value 0.044
redirect.value 0.048
starttransfer.value 0.081
total.value 0.151
```

5) Restart munin-node.

```
# service munin-node restart
Stopping Munin Node agents:                                [  OK  ]
Starting Munin Node:                                       [  OK  ]
```




# Origin

httpレスポンスタイムの内訳をグラフにしてみた | ツチノコブログ
http://tsuchinoko.dmmlabs.com/?p=1442
