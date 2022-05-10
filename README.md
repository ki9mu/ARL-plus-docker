# ARL-plus-docker
基于(https://github.com/TophantTechnology/ARL/)

# 使用方式
进入原版的arl/docker目录，删除原版容器，直接删除即可，数据是存放在volume里，会直接更新到新版
```docker-compose down```

然后拉取本项目，启用即可
```docker-compose up -d```

修改OneForAll相关配置文件

# 新增功能
### 新增OneForAll √
![image](https://user-images.githubusercontent.com/47977616/167526875-0d944261-7bed-4918-936e-38c195ce7f42.png)
### 新增中央数据库 √
使用中央数据库需要外联站点，私聊我加ip白名单，否则该功能无法使用
![image](https://user-images.githubusercontent.com/47977616/167527042-0598791e-6fe8-49e6-b363-a8a040d2cf1d.png)

### 智能子域名优化 √
改了下altDNS
### POC数量 X
这个搞完发现没啥用，增加到200个poc，但一个也没扫出来
