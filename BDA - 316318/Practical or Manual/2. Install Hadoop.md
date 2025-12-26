
---

# Title: Install Hadoop Ecosystem on Local Cluster

---

## 1. Install latest version of Java
```bash
sudo apt update
sudo apt install openjdk-21-jdk
```

Verify Java:

```bash
java -version
```

Set Java to env:

```bash
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$PATH:$JAVA_HOME/bin
```
 
---

## 2. Download and Install Hadoop 

```bash
wget link
```

Extract and move:

```bash
tar -xvzf hadoop-3.3.6.tar.gz
sudo mv hadoop-3.3.6 /usr/local/hadoop
```

---

## 3. Set Hadoop Environment Variables

Edit `.bashrc`:

```bash
nano ~/.bashrc
```

Add:

```bash
export HADOOP_HOME=/usr/local/hadoop
export HADOOP_INSTALL=$HADOOP_HOME
export HADOOP_MAPRED_HOME=$HADOOP_HOME
export HADOOP_COMMON_HOME=$HADOOP_HOME
export HADOOP_HDFS_HOME=$HADOOP_HOME
export YARN_HOME=$HADOOP_HOME
export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native
export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin
```

Apply:

```bash
source ~/.bashrc
```

Verify:

```bash
hadoop version
```

---

## 4. Configure Hadoop

### a) Navigate to hadoop

```bash
cd $HADOOP_HOME/etc/hadoop
```
---

### b) Configure core-site.xml

```bash
nano $HADOOP_HOME/etc/hadoop/core-site.xml
```

```xml
<configuration>
  <property>
    <name>fs.defaultFS</name>
    <value>hdfs://localhost:9000</value>
  </property>
</configuration>
```

---

### c) Configure hdfs-site.xml

```bash
nano $HADOOP_HOME/etc/hadoop/hdfs-site.xml
```

```xml
<configuration>
  <property>
    <name>dfs.replication</name>
    <value>1</value>
  </property>
</configuration>
```

---

### d) Configure mapred-site.xml

```bash
cp $HADOOP_HOME/etc/hadoop/mapred-site.xml.template \
   $HADOOP_HOME/etc/hadoop/mapred-site.xml
nano $HADOOP_HOME/etc/hadoop/mapred-site.xml
```

```xml
<configuration>
  <property>
    <name>mapreduce.framework.name</name>
    <value>yarn</value>
  </property>
</configuration>
```

---

### e) Configure yarn-site.xml

```bash
nano $HADOOP_HOME/etc/hadoop/yarn-site.xml
```

```xml
<configuration>
  <property>
    <name>yarn.nodemanager.aux-services</name>
    <value>mapreduce_shuffle</value>
  </property>
</configuration>
```

---

## 5. Format HDFS

```bash
hdfs namenode -format
```

---

## 6. Start Hadoop Services

Start HDFS and YARN:

```bash
start-dfs.sh
start-yarn.sh
```

Check running services:

```bash
jps
```

You should see:

* NameNode
* DataNode
* ResourceManager
* NodeManager

---

## 7. Access Hadoop Web UI

| Service            | URL                                            |
| ------------------ | ---------------------------------------------- |
| NameNode UI        | [http://localhost:9870](http://localhost:9870) |
| ResourceManager UI | [http://localhost:8088](http://localhost:8088) |

---
