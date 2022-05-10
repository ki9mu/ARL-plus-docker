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

# Q&A
Q: 什么是中央数据库

A: A设备对域名abc.com扫描，发现了子域名aaa.abc.com，会将aaa子域名上传至中央数据库。B设备在进行子域名爆破的时候，会拉取中央数据库中的子域。如果同时也在扫描abc.com，基本子域名不会遗漏。（为啥加这个功能，我发现ARL很多次扫描子域结果都不太一样，也不知道是咋回事，变多还可以理解，变少就不应该吧）

Q: 如何确定自己是否在中央数据库白名单里

A: 随便开启一个域名的扫描，看`DB-GET-Subdomains: 123`和`DB-Update-Subdomains: 123`两个属性是否比较大，第一个一般是3位数，如果个位数说明数据库连接失败了。

Q: 如何使用OneForAll

A: 文件目录下有个oneforall-config文件夹，修改其中配置即可

Q: 为什么扫描aaa.abc.com会出现bbb.abc.com

A: 因为OneForAll的API接口设置，输入aaa.abc.com会有响应bbb.abc.com，介意的话关闭OneForAll模块即可
