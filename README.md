ZookeeperConfigurationCenter
============================

Zookeeper Implemented Configuration Center


It is  a common agreement that the web2.0 era web apps are becoming more and more complication.

Normally the complication web apps are distributed publish, and the Configuration of the applications need to
 be dynamic changed without stop the services. But for many companies the management of those configuration are often harsh work. So a Configuration Center is need for this phenomenon. 

ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed 
synchronization, and providing group services. For this demand, the zookeeper is a ad-hoc Solution for configuration center.

this project is aim at this phenomenon.

Traditionlly our application is publish like this ：

                 ||||||||||||||||||||              |||||||||||||||||||      |||||||||||||||||||||  
                 ||     APP1       ||   ||    APP2       ||      ||     APP3        ||
                 ||||||||||||||||||||   ||||||||||||||||||||     |||||||||||||||||||||
                          |                       |                      |
                          |                       |                      |
                |||||||||||||||||||||	|||||||||||||||||||||    ||||||||||||||||||||
                ||  ConfigFile1	   ||   ||  ConfigFile2	   ||    ||   ConfigFile3  ||
                |||||||||||||||||||||   |||||||||||||||||||||    ||||||||||||||||||||

Those ConfigFiles maybe all the same or maybe not. So we need to design this Configuration Center as the demand.like:

                 ||||||||||||||||||||                 |||||||||||||||||||||||||||||||||||||||||
                 ||     APP1       ||---------------->|          ------------------           |
                 ||||||||||||||||||||                 |         |sharedConfigFiles |          | 
                                                      |          ------------------           |
                                                      |                                       |
                                                      |                                       |
                                                      |          APP2ConfigFile               |
                 ||||||||||||||||||||                 |                                       | 
                 ||     APP2       ||---------------->|                                       |   
                 ||||||||||||||||||||                 |                                       |
                                                      |         APP3ConfigFile                |
                                                      |                                       |	      
                                                      |                                       |
                                                      |                                       |	      
                                                      |          APP1ConfigFile               |
                                                      |                                       |
                 ||||||||||||||||||||                 |                                       | 
                 ||     APP3       ||---------------->|                                       |   
                 ||||||||||||||||||||                 ||||||||||||||||||||||||||||||||||||||||| 



1. sharedConfigFiles will share by all the apps{when implements this share center:the configFile1 maybe    share only by app1 and app3,while configFile2 maybe share by app3 and app4, so the ZK Client Watcher must be well desgined}

2. the APP2 may add to she shareConfig(say app2 was started without sharefile,but later app2 will add to the sharefiles).





                  
