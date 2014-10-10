This is Munin plugin for http response time.


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
[httpresp_curl_www1.example.co.jp]
  env.URL http://www1.example.co.jp/

[httpresp_curl_www2.example.co.jp]
  env.URL http://www2.example.co.jp/
```


3) Link plugin file.

```
# cd /etc/munin/plugins
# ln -s /usr/share/munin/plugins/httpresp_curl_ httpresp_curl_www1.example.co.jp
# ln -s /usr/share/munin/plugins/httpresp_curl_ httpresp_curl_www2.example.co.jp
```


origin

http://tsuchinoko.dmmlabs.com/?p=1442
