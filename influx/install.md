<div  id="i-db" ></div>

# 安装influxDB

## linux

### ubantu

ARM64

```shell
# Ubuntu/Debian ARM64
curl -O https://dl.influxdata.com/influxdb/releases/influxdb2_2.7.5-1_arm64.deb
sudo dpkg -i influxdb2_2.7.5-1_arm64.deb
```

AMD64

```shell
# Ubuntu/Debian AMD64
curl -O https://dl.influxdata.com/influxdb/releases/influxdb2_2.7.5-1_amd64.deb
sudo dpkg -i influxdb2_2.7.5-1_amd64.deb
```

### centOS

ARM64

```shell
# Red Hat/CentOS/Fedora AArch64 (ARMv8-A)
curl -O https://dl.influxdata.com/influxdb/releases/influxdb2-2.7.5-1.aarch64.rpm
sudo yum localinstall influxdb2-2.7.5-1.aarch64.rpm
```

AMD64

```shell
# Red Hat/CentOS/Fedora x86-64 (x64, AMD64)
curl -O https://dl.influxdata.com/influxdb/releases/influxdb2-2.7.5-1.x86_64.rpm
sudo yum localinstall influxdb2-2.7.5-1.x86_64.rpm
```



### 启动influxDB

```shell
sudo service influxdb start
```

#### 💡默认端口：8086

可视化页面：http://127.0.0.1:8086

#### 修改默认端口

通过http-bind-address参数修改

##### 方式1：设置环境变量

```shell
export INFLUXD_HTTP_BIND_ADDRESS=:8086
```

注意：环境变量必须添加到启动服务的用户

##### 方式2：⭐️在配置文件中添加(推荐)

```t
http-bind-address: ":8086"
```

配置文件默认目录

- ubuntu：`/etc/influxdb/config.toml`

##### 方式3：启动参数

```shell
influxd --http-bind-address=:8086
```

<div  id="i-cli" ></div>

# 安装influx CLI（命令行客户端）

## linux

**获取最新版本：https://github.com/influxdata/influx-cli/releases

截止2024.4.8最新版本为2.7.3

### ARM

```shell
# amd64
# 下载
wget https://dl.influxdata.com/influxdb/releases/influxdb2-client-2.7.3-linux-arm64.tar.gz
# 解压
tar xvzf ./influxdb2-client-2.7.3-linux-arm64.tar.gz
# 添加到$PATH中
sudo cp ./influx /usr/local/bin/
```

### AMD

```shell
# amd64
# 下载
wget https://dl.influxdata.com/influxdb/releases/influxdb2-client-2.7.3-linux-amd64.tar.gz
# 解压
tar xvzf ./influxdb2-client-2.7.3-linux-amd64.tar.gz
# 添加到$PATH中
sudo cp ./influx /usr/local/bin/
```

### 使用

```shell 
influx -h
```
