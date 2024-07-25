# ARL-plus-docker
基于ARL-V2.6.2版本自研
ARL的安装这里就不多赘述了，可以看这里 https://github.com/ki9mu/ARL-plus-docker/blob/dev/ARL-README.md

# 免责声明
如果您下载、安装、使用、修改本系统及相关代码，即表明您信任本系统。在使用本系统时造成对您自己或他人任何形式的损失和伤害，我们不承担任何责任。 如您在使用本系统的过程中存在任何非法行为，您需自行承担相应后果，我们将不承担任何法律及连带责任。 请您务必审慎阅读、充分理解各条款内容，特别是免除或者限制责任的条款，并选择接受或不接受。 除非您已阅读并接受本协议所有条款，否则您无权下载、安装或使用本系统。您的下载、安装、使用等行为即视为您已阅读并同意上述协议的约束。

# 新增功能
1. 中央数据库（数据库逻辑大改，整个过程会非常丝滑）
2. 修改了rabbitmq的超时时间，可能重型任务不会挂？（实测4c8g跑qq.com，跑了1个月都没挂，最终跑完了，如果还挂应该是服务器配置不行，加钱解决一切问题）
3. 没了...(有需求提issue，视情况开发)
4. 新版本功能开发中（敬请期待）

# 安装方式
首次安装：
```
docker volume create arl_db
```
更新安装
```
docker-compose down
docker-compose up -d
```
PS:
由于近期dockerHub问题，现将相关镜像放到网盘，可解压为.tar文件后执行`docker load -i xxx.tar`即可部署，可在公众号回复`ARL-plus`获取地址


# 中央数据库介绍
默认关闭
开启方式：
```
vim config-docker.yaml
# 最底部的center_option设置为true即可，默认为false
# 如果有不想上传的扫描，可以在扫描前设置为false，执行docker-compose restart重启容器，扫描完成后再改回true并重启容器即可。
```

# 写在最后
n久没写了，几乎重写，难顶

# 如果拉取镜像失败

原因：GWF懂得都懂
解决方法：
1. 挂代理
2. 使用代理服务器拉取镜像，然后打包成压缩包，并上传

# 服务器推荐
推荐腾讯云或京东云的4C8G 5M以上的配置，目前性价比最高的是京东云的4C8G 518/年（可以将任务改成3或者4），也可以买腾讯云68/年的2C2G（任务改成1）
[京东云]
[腾讯云]
更改方式
```
vim docker-compose.yml
找到arltask -c 2，这里的-c参数就是任务并行数量，通常这个值是cpu核心数-1
```
![image](https://github.com/user-attachments/assets/891bfa62-d130-4e1b-a269-678fc8659bcd)


# 团队微信
![b4fd06ae7fb4d6a977754f3077c7274](https://github.com/ki9mu/ARL-plus-docker/assets/47977616/48ec6b67-dcaa-4f59-b845-b3d3ede31eda)


[京东云快捷方式]: https://3.cn/-22ITTEy
[腾讯云]: https://cloud.tencent.com/act/cps/redirect?redirect=5333&cps_key=488ad3cc44ae37630a493f684f3dc296&from=console
