
### 特点

一键安装 Shadowsocks-Python， ShadowsocksR， Shadowsocks-Go， Shadowsocks-libev 版（四选一）服务端


### 安装方法

安装wget
```
# centos
yum -y install wget

# Ubuntu
apt-get -y install wget
```

安装服务
```
wget --no-check-certificate https://raw.githubusercontent.com/leeairw/shadowsocks-all/master/install/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```

默认密码`abc123456`

### 卸载方法

若已安装多个版本，则卸载时也需多次运行（每次卸载一种）

使用root用户登录，运行以下命令：

./shadowsocks-all.sh uninstall 如果安装了多种，那么也需要卸载多次
启动脚本

### 操作方法
启动脚本后面的参数含义，从左至右依次为：启动，停止，重启，查看状态。

Shadowsocks-Python 版：
```
/etc/init.d/shadowsocks-python start
/etc/init.d/shadowsocks-python stop
/etc/init.d/shadowsocks-python restart
/etc/init.d/shadowsocks-python status
```

ShadowsocksR 版： 
```
/etc/init.d/shadowsocks-r start
/etc/init.d/shadowsocks-r stop
/etc/init.d/shadowsocks-r restart
/etc/init.d/shadowsocks-r status
```

Shadowsocks-Go 版： 
```
/etc/init.d/shadowsocks-go start
/etc/init.d/shadowsocks-go stop
/etc/init.d/shadowsocks-go restart
/etc/init.d/shadowsocks-go status
```

Shadowsocks-libev 版： 
```
/etc/init.d/shadowsocks-libev start
/etc/init.d/shadowsocks-libev stop
/etc/init.d/shadowsocks-libev restart
/etc/init.d/shadowsocks-libev status
```

### 各版本默认配置文件

Shadowsocks-Python 版： 
```
/etc/shadowsocks-python/config.json
```

ShadowsocksR 版： 
```
/etc/shadowsocks-r/config.json
```

Shadowsocks-Go 版： 
```
/etc/shadowsocks-go/config.json
```

Shadowsocks-libev 版： 
```
/etc/shadowsocks-libev/config.json
```

### 多用户配置方法

修改上述对应的对应的config.json如下 并且保存 { "server":"my_server_ip", #填入你的IP地址 "local_address": "127.0.0.1", "local_port":1080, "port_password": { "8381": "foobar1", #端口号，密码 "8382": "foobar2", "8383": "foobar3", "8384": "foobar4" }, "timeout":300, "method":"aes-256-cfb", "fast_open": false }

建议了解vim 编辑器相应的指令，快速上手， vi filename 打开文件名为filename的文件，如果没有就会新建一个名为filename的文件，按esc 输入：i 表示会插入某些字符 输入完，按esc 进入命令控制模式 输入wq!表示强制退出并保存。 vi config.json
