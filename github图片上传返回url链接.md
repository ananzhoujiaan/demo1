说明：
```
'''
第一步：上传文件到img目录下
第二步：读取上传文件夹的文件名
第三步：将文件上传到github文件夹下返回url链接
第四步：设置sh快捷启动、设置py为开机自启
'''
```
rz filename

##true.py
```
#!/usr/bin/env python
# -*- coding: utf-8 -*-
import os
from watchdog.observers import Observer
from watchdog.events import *
import time
class FileEventHandler(FileSystemEventHandler):
    def __init__(self):
        FileSystemEventHandler.__init__(self)
    def on_created(self, event):
        with open('/var/log/img.log','a+') as f:
           # line=event.src_path +"\n"
            f.write(event.src_path+"\n")  
if __name__ == "__main__":
    observer = Observer()
    event_handler = FileEventHandler()
    observer.schedule(event_handler,"/img",True)
    observer.start()
    try:
        while True:
            time.sleep(1)
    except KeyboardInterrupt:
        observer.stop()
    observer.join()
```
##文件上传返回url链接

##true.sh
```
#!/bin/bash
fileline=`tail -n 1 /var/log/img.log|awk -F '/' '{print $3}'`
git add /img/$fileline >/dev/null 2>&1
git commit -a -m 'add $fileline' >/dev/null 2>&1
git push origin master >/dev/null 2>&1
echo https://raw.githubusercontent.com/ananzhoujiaan/img/master/$fileline
```

##添加开机自启动命令：
```
chmod +x /etc/rc.d/rc.local\
vi /etc/rc.d/rc.local #添加开机启动命令
```