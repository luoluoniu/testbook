# 21.1.3 服务异常处理

1. 若启动服务超时，则可以在启动服务的命令行中加入--timeout 400增加启动超时时限，例如 `zstack_ctl start_node –timeout 400`

2. 执行`zstack-ctl status`检查服务的状态，根据相应提示查看management-server.log，定位问题所在。也可以将该log文件打包交到Mevoco官网用户讨论组中获取更多帮助。

3. 若需重启Mevoco服务，请执行`zstack-ctl stop; zstack-ctl start`

