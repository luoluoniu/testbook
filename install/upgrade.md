# 3.3 升级Mevoco

使用ZStack 或者Mevoco 较低版本的用户可以直接升级到最新版本的Mevoco。

1.升级前，请注意备份数据库。Mevoco目前已支持自动备份数据库，在安装完毕Mevoco后，系统自动配置了crontab自动定时备份数据库任务，默认备份如下所示：

```
[root@localhost ~]#crontab -l
30 0,12 * * * zstack-ctl dump_mysql --keep-amount 14
#表示每天夜间12点半和中午12点半进行数据库备份，并保存最新的14次备份
数据库自动备份的目录为：/var/lib/zstack/mysql-backup
```

2.升级将会默认保留配置，请指定参数-u，例如，执行`bash mevoco-installer.bin -u。`

3.如果升级前的系统安装采用了ZStack定制版低版本的ISO（例如1.3版本），在升级Mevoco前，需要参考19.12升级ZStack定制版ISO的Yum源到最新版本。

4.如果升级前的系统安装采用了ZStack定制版ISO，那么升级时请指定参数‘-o’。

5.如果升级时希望使用aliyun官方yum源，请指定参数：‘-R aliyun’。

6.如果升级前Mevoco是运行状态，升级完成后，升级程序也将会启动Mevoco，如果升级前服务是停止状态，需手动启动Mevoco服务。

7.如果从ZStack升级到Mevoco，在升级时，请指定参数：‘-u’。

注意：升级过程中遇到的异常，请参考升级异常处理。

