# ARL-plus-docker
基于(https://github.com/TophantTechnology/ARL/)

# 原版更新方式
进入原版的arl/docker目录，删除原版容器，直接删除即可，数据是存放在volume里，会直接更新到新版
```docker-compose down```

然后拉取本项目，启用即可
```docker-compose up -d```

修改OneForAll相关配置文件

# 新版更新方式
到本项目路径下`git pull`

然后```docker-compose up -d```

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

A: 随便开启一个域名的扫描，看`domain_brute: 300`属性是否比较大，一般是几百，如果个位数或者十几秒就结束了，说明数据库连接失败了。

Q: 如何添加中央数据库白名单

A: 邮件发送ip给ki9mu@qq.com即可

Q: 如何使用OneForAll

A: 文件目录下有个oneforall-config文件夹，修改其中配置即可

Q: 为什么扫描aaa.abc.com会出现bbb.abc.com

A: 因为OneForAll的API接口设置，输入aaa.abc.com会有响应bbb.abc.com，介意的话关闭OneForAll模块即可（目前对oneforall结果进行了过滤，已无该bug）

Q: 任务为什么有时候会卡死

A: 多种原因。可以看下当前目录下arl_web.log/arl_worker.log日志文件是否过大，删除容器及日志文件重新拉取项目。启用oneforall的时候可能导致该问题。低配置服务器运行也可能导致该问题(本人是4c4g基本正常使用)
