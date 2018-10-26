---
layout: post
title: "Jmeter-Linux environment setup(2)-Jemeter deployment"
---

1. load Jmeter package(https://jmeter.apache.org/download_jmeter.cgi) to Linux
    I choose folder /usr/data to local Jmeter package

2. unpackage Jmeter to /usr/data

3. configurate Jmeter environment variables then make setting effective
    insert following content into /etc/profile:
        # User specific environment and startup programs
        export JMETER_HOME=/data/qa-smjr/jmeter/apache-jmeter-3.0.2
        export CLASSPATH=$JMETER_HOME/lib/ext/ApacheJMeter_core.jar:$JMETER_HOME/lib/jorphan.jar:$JMETER_HOME/lib/logkit-2.0.jar:$CLASSPATH
        export PATH=$JMETER_HOME/bin:$PATH:$HOME/bin

4. use command 'jmeter --version' to test if Jmeter be deployed successfully

REFERENCE: https://www.cnblogs.com/jessicaxu/p/7555046.html
