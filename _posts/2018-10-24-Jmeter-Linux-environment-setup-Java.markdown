---
layout: post
title: "Jmeter-Linux environment setup(1)-Java deployment"
---

1. download jdk package for Linux
    jdk8 is from https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
    note: use command "getconf LONG_BIT" to get system bit for Linux system
    
2. make jdk package to /usr/local/java folder and unzip package
    commands: mv jdk-8u191-linux-x64.tar.gz /usr/local/java
              cd /usr/local/java
              tar -zxvf jdk-8u191-linux-x64.tar.gz

3. config environment variable
    commands: vi /etc/profile 
    and add following content:
      #Java Env
      export JAVA_HOME=/usr/jdk1.8.0_191 (depends on the jdk package version)
      export JRE_HOME=/usr/jdk1.8.0_191/jre
      export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib
      export PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin

4. check JAVA deployment
    commands: java -version
    
ONE THING need more investigation: i used root user to deploy JDK but when using 'java -version' to check deployment status, cannot 
get java version. And i used my own user to test, it works!


