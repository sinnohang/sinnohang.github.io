2023-09-26 22:45:23,523 INFO  [main] master.HMaster: hbase.rootdir=hdfs://hadoopyqh643:9000/hbase, hbase.cluster.distributed=true
2023-09-26 22:45:23,539 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] master.HMaster: Adding backup master ZNode /hbase/backup-masters/hadoopyqh643,16000,1695739520606
2023-09-26 22:45:23,598 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] master.ActiveMasterManager: Deleting ZNode for /hbase/backup-masters/hadoopyqh643,16000,1695739520606 from backup master directory
2023-09-26 22:45:23,600 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] master.ActiveMasterManager: Registered as active master=hadoopyqh643,16000,1695739520606
2023-09-26 22:45:24,073 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] fs.HFileSystem: Added intercepting call to namenode#getBlockLocations so can do block reordering using class org.apache.hadoop.hbase.fs.HFileSystem$ReorderWALBlocks
2023-09-26 22:45:24,081 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] coordination.SplitLogManagerCoordination: Found 0 orphan tasks and 0 rescan nodes
2023-09-26 22:45:24,156 INFO  [ReadOnlyZKClient-hadoopyqh643:2181@0x52734c30] zookeeper.ZooKeeper: Initiating client connection, connectString=hadoopyqh643:2181 sessionTimeout=90000 watcher=org.apache.hadoop.hbase.zookeeper.ReadOnlyZKClient$$Lambda$52/1134819629@6a16f3d
2023-09-26 22:45:24,158 INFO  [ReadOnlyZKClient-hadoopyqh643:2181@0x52734c30-SendThread(hadoopyqh643:2181)] zookeeper.ClientCnxn: Opening socket connection to server hadoopyqh643/192.168.10.100:2181. Will not attempt to authenticate using SASL (unknown error)
2023-09-26 22:45:24,158 INFO  [ReadOnlyZKClient-hadoopyqh643:2181@0x52734c30-SendThread(hadoopyqh643:2181)] zookeeper.ClientCnxn: Socket connection established to hadoopyqh643/192.168.10.100:2181, initiating session
2023-09-26 22:45:24,161 INFO  [ReadOnlyZKClient-hadoopyqh643:2181@0x52734c30-SendThread(hadoopyqh643:2181)] zookeeper.ClientCnxn: Session establishment complete on server hadoopyqh643/192.168.10.100:2181, sessionid = 0x18ad1ee493e0003, negotiated timeout = 90000
2023-09-26 22:45:24,206 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] procedure2.ProcedureExecutor: Starting 16 core workers (bigger of cpus/4 or 16) with max (burst) worker count=160
2023-09-26 22:45:24,213 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] util.FSHDFSUtils: Recover lease on dfs file hdfs://hadoopyqh643:9000/hbase/MasterProcWALs/pv2-00000000000000000002.log
2023-09-26 22:45:24,221 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] util.FSHDFSUtils: Recovered lease, attempt=0 on file=hdfs://hadoopyqh643:9000/hbase/MasterProcWALs/pv2-00000000000000000002.log after 8ms
2023-09-26 22:45:24,221 WARN  [master/hadoopyqh643:16000:becomeActiveMaster] wal.WALProcedureStore: Remove uninitialized log: FileStatus{path=hdfs://hadoopyqh643:9000/hbase/MasterProcWALs/pv2-00000000000000000002.log; isDirectory=false; length=0; replication=3; blocksize=134217728; modification_time=1695737212799; access_time=1695737211024; owner=atguigu; group=supergroup; permission=rw-r--r--; isSymlink=false}
2023-09-26 22:45:24,221 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] wal.ProcedureWALFile: Archiving hdfs://hadoopyqh643:9000/hbase/MasterProcWALs/pv2-00000000000000000002.log to hdfs://hadoopyqh643:9000/hbase/oldWALs/pv2-00000000000000000002.log
2023-09-26 22:45:24,240 ERROR [master/hadoopyqh643:16000:becomeActiveMaster] master.HMaster: Failed to become active master
java.lang.IllegalStateException: The procedure WAL relies on the ability to hsync for proper operation during component failures, but the underlying filesystem does not support doing so. Please check the config value of 'hbase.procedure.store.wal.use.hsync' to set the desired level of robustness and ensure the config value of 'hbase.wal.dir' points to a FileSystem mount that can provide it.
	at org.apache.hadoop.hbase.procedure2.store.wal.WALProcedureStore.rollWriter(WALProcedureStore.java:1092)
	at org.apache.hadoop.hbase.procedure2.store.wal.WALProcedureStore.recoverLease(WALProcedureStore.java:424)
	at org.apache.hadoop.hbase.procedure2.ProcedureExecutor.init(ProcedureExecutor.java:576)
	at org.apache.hadoop.hbase.master.HMaster.createProcedureExecutor(HMaster.java:1528)
	at org.apache.hadoop.hbase.master.HMaster.finishActiveMasterInitialization(HMaster.java:938)
	at org.apache.hadoop.hbase.master.HMaster.startActiveMasterManager(HMaster.java:2112)
	at org.apache.hadoop.hbase.master.HMaster.lambda$run$0(HMaster.java:580)
	at java.lang.Thread.run(Thread.java:748)
2023-09-26 22:45:24,241 ERROR [master/hadoopyqh643:16000:becomeActiveMaster] master.HMaster: ***** ABORTING master hadoopyqh643,16000,1695739520606: Unhandled exception. Starting shutdown. *****
java.lang.IllegalStateException: The procedure WAL relies on the ability to hsync for proper operation during component failures, but the underlying filesystem does not support doing so. Please check the config value of 'hbase.procedure.store.wal.use.hsync' to set the desired level of robustness and ensure the config value of 'hbase.wal.dir' points to a FileSystem mount that can provide it.
	at org.apache.hadoop.hbase.procedure2.store.wal.WALProcedureStore.rollWriter(WALProcedureStore.java:1092)
	at org.apache.hadoop.hbase.procedure2.store.wal.WALProcedureStore.recoverLease(WALProcedureStore.java:424)
	at org.apache.hadoop.hbase.procedure2.ProcedureExecutor.init(ProcedureExecutor.java:576)
	at org.apache.hadoop.hbase.master.HMaster.createProcedureExecutor(HMaster.java:1528)
	at org.apache.hadoop.hbase.master.HMaster.finishActiveMasterInitialization(HMaster.java:938)
	at org.apache.hadoop.hbase.master.HMaster.startActiveMasterManager(HMaster.java:2112)
	at org.apache.hadoop.hbase.master.HMaster.lambda$run$0(HMaster.java:580)
	at java.lang.Thread.run(Thread.java:748)
2023-09-26 22:45:24,241 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] regionserver.HRegionServer: ***** STOPPING region server 'hadoopyqh643,16000,1695739520606' *****
2023-09-26 22:45:24,241 INFO  [master/hadoopyqh643:16000:becomeActiveMaster] regionserver.HRegionServer: STOPPED: Stopped by master/hadoopyqh643:16000:becomeActiveMaster
2023-09-26 22:45:25,081 INFO  [master/hadoopyqh643:16000.splitLogManager..Chore.1] hbase.ScheduledChore: Chore: SplitLogManager Timeout Monitor was stopped
2023-09-26 22:45:26,608 INFO  [master/hadoopyqh643:16000] ipc.NettyRpcServer: Stopping server on /192.168.10.100:16000
2023-09-26 22:45:26,615 INFO  [master/hadoopyqh643:16000] regionserver.HRegionServer: Stopping infoServer
2023-09-26 22:45:26,620 INFO  [master/hadoopyqh643:16000] handler.ContextHandler: Stopped o.e.j.w.WebAppContext@474c9131{/,null,UNAVAILABLE}{file:/opt/hbase/hbase-webapps/master}
2023-09-26 22:45:26,623 INFO  [master/hadoopyqh643:16000] server.AbstractConnector: Stopped ServerConnector@407873d3{HTTP/1.1,[http/1.1]}{0.0.0.0:16010}
2023-09-26 22:45:26,623 INFO  [master/hadoopyqh643:16000] handler.ContextHandler: Stopped o.e.j.s.ServletContextHandler@4aedaf61{/static,file:///opt/hbase/hbase-webapps/static,UNAVAILABLE}
2023-09-26 22:45:26,623 INFO  [master/hadoopyqh643:16000] handler.ContextHandler: Stopped o.e.j.s.ServletContextHandler@2f508f3c{/logs,file:///opt/hbase/logs/,UNAVAILABLE}
2023-09-26 22:45:26,624 INFO  [master/hadoopyqh643:16000] regionserver.HRegionServer: aborting server hadoopyqh643,16000,1695739520606
2023-09-26 22:45:26,624 INFO  [master/hadoopyqh643:16000] regionserver.HRegionServer: stopping server hadoopyqh643,16000,1695739520606; all regions closed.
2023-09-26 22:45:26,624 INFO  [master/hadoopyqh643:16000] hbase.ChoreService: Chore service for: master/hadoopyqh643:16000 had [] on shutdown
2023-09-26 22:45:26,625 INFO  [ReadOnlyZKClient-hadoopyqh643:2181@0x52734c30] zookeeper.ZooKeeper: Session: 0x18ad1ee493e0003 closed
2023-09-26 22:45:26,625 WARN  [master/hadoopyqh643:16000] master.ActiveMasterManager: Failed get of master address: java.io.IOException: Can't get master address from ZooKeeper; znode data == null
2023-09-26 22:45:26,626 INFO  [ReadOnlyZKClient-hadoopyqh643:2181@0x52734c30-EventThread] zookeeper.ClientCnxn: EventThread shut down for session: 0x18ad1ee493e0003
2023-09-26 22:45:26,626 INFO  [master/hadoopyqh643:16000] wal.WALProcedureStore: Stopping the WAL Procedure Store, isAbort=true
2023-09-26 22:45:26,627 INFO  [master/hadoopyqh643:16000] hbase.ChoreService: Chore service for: master/hadoopyqh643:16000.splitLogManager. had [] on shutdown
2023-09-26 22:45:26,629 INFO  [master/hadoopyqh643:16000] zookeeper.ZooKeeper: Session: 0x18ad1ee493e0002 closed
2023-09-26 22:45:26,629 INFO  [master/hadoopyqh643:16000] regionserver.HRegionServer: Exiting; stopping=hadoopyqh643,16000,1695739520606; zookeeper connection closed.
2023-09-26 22:45:26,629 ERROR [main] master.HMasterCommandLine: Master exiting
java.lang.RuntimeException: HMaster Aborted
	at org.apache.hadoop.hbase.master.HMasterCommandLine.startMaster(HMasterCommandLine.java:244)
	at org.apache.hadoop.hbase.master.HMasterCommandLine.run(HMasterCommandLine.java:140)
	at org.apache.hadoop.util.ToolRunner.run(ToolRunner.java:76)
	at org.apache.hadoop.hbase.util.ServerCommandLine.doMain(ServerCommandLine.java:149)
	at org.apache.hadoop.hbase.master.HMaster.main(HMaster.java:2942)
2023-09-26 22:45:26,629 INFO  [main-EventThread] zookeeper.ClientCnxn: EventThread shut down for session: 0x18ad1ee493e0002