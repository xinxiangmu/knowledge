# 常见问题
-在install 安装的过程中idea的插件不行，需要使用这个执行
* https://blog.csdn.net/gao_zhennan/article/details/89713407
- maven 时报错The packaging for this project did not assign a file to the build artifact 
* 主要是因为idea插件和mvn之间的区别，查看这个  https://www.cnblogs.com/Jeely/p/11301162.html 
- mvn clean install mvn clean install:install 区别是前者是install，后者是执行的目标，所以需要注意
- dubbo 依赖的jar包启动的时候和配置的包版本不同，例如依赖的dubbo 3.0.8版本的，对应的cura是4.x版本但是在实际的使用的时候使用的是5.x版本导致出现版本不一致问题
- 其中dubbo的jar pom为proiver，就是要运行环境提供，但是我这边是在idea上，所以会自动依赖为5.x导致版本问题，在run 参数上添加idea的 add dependencies with  proiver scode to  classpath
-  <revision>1.0.0-SNAPSHOT</revision> snapsho

