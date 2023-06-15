##### 版本选择
- [Java Archive Downloads - Java SE 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)
``` c
wget https://download.oracle.com/java/17/archive/jdk-17.0.7_linux-x64_bin.tar.gz
tar -zxvf https://download.oracle.com/java/17/archive/jdk-17.0.7_linux-x64_bin.tar.gz -C /usr/local
pwd 
# /usr/local/jdk-17.0.7
cd ~
vim ~/.bashrc 
####添加
export JAVA_HOME=/usr/local/jdk-17.0.7
export JRE_HOME=${JAVA_HOME}/jre
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH
####
# 让配置生效
source ~/.bashrc

```

