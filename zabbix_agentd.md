## Ubuntu 10.04

请参考《zabbix on Ubuntu 10.04》一文

## CentOS 5

可以通过源码编译的方式安装最新版的zabbix_agentd，但是那样太过耗时耗力，好在有热心的网友为我们编译了较新版本的zabbix，我们直接下载安装即可。

### 下载
 
        # cd /software
        # wget http://download.opensuse.org/repositories/home:/ericgearhart:/zabbix/CentOS_CentOS-5/x86_64/zabbix-1.8.9-6.1.x86_64.rpm
        # wget http://download.opensuse.org/repositories/home:/ericgearhart:/zabbix/CentOS_CentOS-5/x86_64/zabbix-agent-1.8.9-6.1.x86_64.rpm

> **说明**：
>
>该热心的网友时不时会更新至最新的版本，目前是zabbix-1.8.9。

### 安装

	# rpm -ivh zabbix-1.8.9-6.1.x86_64.rpm
	# rpm -ivh zabbix-agent-1.8.9-6.1.x86_64.rpm

### 配置
	
	# vim /etc/zabbix/zabbix_agentd.conf
	...
	Server=<your zabbix_server's ip>
	
### 启动

	# /etc/init.d/zabbix_agentd start

可以通过

	# netstat -an | grep 10050
	# ps aux | grep zabbix_agentd

来检查是否正常启动，当然也可以通过log日志来排错。

## OpenBSD 4.9

### 安装

OpenBSD4.9的port里面有zabbix_agent-1.8.3，直接通过`pkg_add -i zabbix-agent-1.8`即可完成安装。

### 配置

修改`/etc/zabbix/zabbix_agentd.conf`

	...
	Server=<your zabbix_server's ip>
	LogFile=/var/log/zabbix/zabbix_agentd.log
	PidFile=/var/run/zabbix/zabbix_agentd.pid

接着创建相应的目录和文件

    # mkdir /var/log/zabbix && touch /var/log/zabbix/zabbix_agentd.log
    # chown -R zabbix:zabbix /var/run/zabbix
    # chown -R zabbix:zabbix /var/log/zabbix

### 启动

    # /etc/rc.d/zabbix_agentd start

### 测试

* 测试是否正常启动

    # ps aux | grep zabbix
    # netstat -an | grep 10050

* 从服务器端测试是否可以正常工作

    zabbix server# zabbix_get -s <zabbix_agent ip> -k "system.uname"
 
