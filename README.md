### ranger client to be used by cosn and chdfs plugin

1. 部署方式(通常放在和cosn插件以及chdfs插件的同一目录下)
2. 配置项(配置项位于core-site.xml)
```xml
     <configuration>
           <!--**************************************必须配置**********************-->
           <!-- zk的地址, 客户端从zk上查询得知ranger-service的服务地址 -->
           <property>
                   <name>qcloud.object.storage.zk.address</name>
                   <value>10.0.0.8:2121</value>
           </property>

           <property>
                   <name>qcloud.object.storage.kerberos.principal</name>
                   <value>hadoop/_HOST@EMR-DEFRHX4M</value>
           </property>


            
           <!--**********************可选配置***************************************-->
          <!-- zk上记录的ranger server的ip 地址路径, 这里使用了默认值, 配置必须与cos-ranger-service的配置一致 -->
          <property>
                   <name>qcloud.object.storage.zk.leader.ip.path</name>
                   <value>/ranger_qcloud_object_storage_leader_ip</value>
          </property>
     </configuration>
```