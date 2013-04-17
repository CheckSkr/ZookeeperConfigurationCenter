ZookeeperConfigurationCenter
============================

Zookeeper Implemented Configuration Center


It is a common agreement that the web2.0 era web apps are becoming more and more complication.

Normally the complication web apps are distributed publish, and the Configuration of the applications need to be dynamic changed without stop the services. But for many companies the management of those configuration are often harsh work. So a Configuration Center is need for this phenomenon.

ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services. For this demand, the zookeeper is a ad-hoc Solution for configuration center.

this project is aim at this phenomenon.

Traditionlly our application is publish like this ：

             ||||||||||||||||||||   |||||||||||||||||||      |||||||||||||||||||||  
             ||     APP1       ||   ||    APP2       ||      ||     APP3        ||
             ||||||||||||||||||||   ||||||||||||||||||||     |||||||||||||||||||||
                      |                       |                      |
                      |                       |                      |
            |||||||||||||||||||||   |||||||||||||||||||||    ||||||||||||||||||||
            ||  ConfigFile1    ||   ||  ConfigFile2    ||    ||   ConfigFile3  ||
            |||||||||||||||||||||   |||||||||||||||||||||    ||||||||||||||||||||
Those ConfigFiles maybe all the same or maybe not. So we need to design this Configuration Center as the demand.
