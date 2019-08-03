FROM		centos
MAINTAINER	kszsa<duyonghuibo007@163.com>
#添加环境变量
#JDK和tomcat安装路径
ENV INSTALLDIR /usr/local
#用户登入系统时的工作目录
ENV CURRENT_WORKDIR $INSTALLDIR
#JDK安装包的名称
ENV JDK_NAME jdk-7u80-linux-x64.tar.gz
#tomcat安装包的名称
ENV TOMCAT_NAME apache-tomcat-7.0.96.tar.gz
#配置JDK和tomcat的环境变量
ENV JAVA_HOME=$INSTALLDIR/jdk1.7.0_80
ENV CATALINA_HOME=$INSTALLDIR/apache-tomcat-7.0.96
ENV CATALINA_BASE=$INSTALLDIR/apache-tomcat-7.0.96
ENV CLASSPATH $JAVA_HOME/lib/dt.jar:%JAVA_HOME/lib/tools.jar
ENV PATH $JAVA_HOME/bin:$CATALINA_HOME/bin:$CATALINA_HOME/lib:$PATH

#设置当前工作目录
WORKDIR $CURRENT_WORKDIR
#把JDK和tomcat添加到容器,并解压
ADD jdk-7u80-linux-x64.tar.gz $INSTALLDIR
ADD apache-tomcat-7.0.96.tar.gz $INSTALLDIR
#容器运行时监听的端口
EXPOSE	8080
#容器启动时运行tomcat
CMD $CATALINA_HOME/bin/startup.sh && tail -F $CATALINA_HOME/logs/catalina.out


