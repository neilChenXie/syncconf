syncconf
========

使用ZooKeeper同步集群配置

## Desc

zk.sync.UpdateConf.resetZnodeData  重置节点数据，测试用
zk.sync.UpdateConf.setZKDataByConf 更新配置到 znode
zk.sync.Executor 客户端同步进程


## Step

将 Executor、DataMonitor、Constant、ConfFileUtil 打包为 confsync.jar
放到所有需要同步更新配置的节点


|--confsync.jar

|------lib------|-slf4j-api-1.6.1.jar

|---------------|-zookeeper-3.4.5.jar

运行 Executor：
 java -classpath ".:confsync.jar:lib/*" zk.sync.Executor
需要更新 yarn-site.xml 时,运行 UpdateConf.setZKDataByConf 更新 znode 节点数据即可
