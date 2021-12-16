# dubbo-admin 镜像

此镜像为 dubbo-admin-2.5.10.war 的docker镜像，支持查看指定组。

参考 [chenchuxin/dubbo-admin-docker](https://github.com/chenchuxin/dubbo-admin-docker)

## 打镜像
```
docker build --rm -t dubbo-admin:2.5.10 .
```

## 启动

```
# dubbo.registry.address ：zk 地址
# dubbo.registry.group ：zk 组

docker run -d --name dubbo-admin \
-p 8080:8080 \
-e dubbo.registry.address=zookeeper://127.0.0.1:2181 \
-e dubbo.registry.group=dubbo \
-e dubbo.admin.root.password=root \
-e dubbo.admin.guest.password=guest \
dubbo-admin:2.5.10 
```

* 运行成功后，稍等一下，访问ip:port即可。
* 默认账号密码是
    * 管理员：root：root
    * 游客：guest：guest

