# Nginx学习

# 介绍

Nginx 是一款轻量级的 Web 服务器 、反向代理服务器。

## 正向代理

> 常见的VPN服务器就是正向代理

![image-20200223150417467](http://img.zhaojishun.cn/img/image-20200223150417467.png)

## 反向代理

> 反向代理（Reverse Proxy）方式是指以代理服务器来接受 internet 上的连接请求，然后将请求转发给内部网络上的服务器，并将从服务器上得到的结果返回给 internet 上请求连接的客户端，此时代理服务器对外就表现为一个反向代理服务器。

# 安装

## 一、依赖库文件安装

```text
yum -y install make zlib zlib-devel gcc-c++ libtool  openssl openssl-devel
```

## 二、安装 PCRE

1、 下载pcre

```text
wget http://downloads.sourceforge.net/project/pcre/pcre/8.35/pcre-8.35.tar.gz
```

2、解压安装包

```
tar zxvf pcre-8.35.tar.gz
```

3、 进入安装目录编译安装

```text
cd pcre-8.35
./configure
make && make install
```

4、 查看pcre版本

```
pcre-config --version
```

![image-20200223150351123](http://img.zhaojishun.cn/img/image-20200223165030656.png)

## 三、 安装nginx

1、 下载nginx [nginx官网](http://nginx.org/)，或者wget

```
wget http://nginx.org/download/nginx-1.12.2.tar.gz
```

2、 解压

```
tar zxvf nginx-1.12.2.tar.gz
```

3、 进入解压缩目录

```
cd nginx-1.12.2/
```

4、 编译安装

```
./configure
make && make install
```

> 到此nginx安装完成

![image-20200223165030656](http://img.zhaojishun.cn/img/image-20200223150351123.png)

# 常用命令

## 防火墙相关

1、查看firewall开放的端口号

```
firewall-cmd --list-all
```

2、开放端口、移除端口

```
firewall-cmd --add-port=80/tcp --permanent
firewall-cmd --permanent --remove-port=80/tcp
```

3、 重启firewall防火墙

```
firewall-cmd --reload
```

4、 查看firewall服务状态

```
systemctl status firewalld
```

5、 查看firewall的状态

```
firewall-cmd --state
```

## nginx相关

```
cd /usr/local/nginx/sbin/
```

### 一、启动

```
./nginx
```

### 二、关闭

```
./nginx -s stop
```

### 三、 重新加载

重新加载不需要关闭nginx

```
./nginx -s reload
```

### 四、其他

```text
nginx -c filename   为 Nginx 指定一个配置文件，来代替缺省的。
nginx -t            不运行，而仅仅测试配置文件。nginx 将检查配置文件的语法的正确性，并尝试打开配置文件中所引用到的文件。
nginx -V            显示 nginx 的版本，编译器版本和配置参数。
```

# 配置文件

> 配置文件存放在安装目录的conf目录下`/usr/local/nginx/conf/nginx.conf`
>
> 后续对nginx 的使用基本上都是对此配置文件进行相应的修改

![image-20200224143721921](http://img.zhaojishun.cn/img/image-20200223171407665.png)

```
#全局设置
main 
# 运行用户
user www-data;    
# 启动进程,通常设置成和cpu的数量相等
worker_processes  1;
# 全局错误日志及PID文件
error_log  /var/log/nginx/error.log;
pid        /var/run/nginx.pid;
# 工作模式及连接数上限
events {
    use epoll; #epoll是多路复用IO(I/O Multiplexing)中的一种方式,但是仅用于linux2.6以上内核,可以大大提高nginx的性能
    worker_connections 1024; #单个后台worker process进程的最大并发链接数
    # multi_accept on; 
}
#设定http服务器，利用它的反向代理功能提供负载均衡支持
http {
    #设定mime类型,类型由mime.type文件定义
    include       /etc/nginx/mime.types;
    default_type  application/octet-stream;
    #设定日志格式
    access_log    /var/log/nginx/access.log;
    #sendfile 指令指定 nginx 是否调用 sendfile 函数（zero copy 方式）来输出文件，对于普通应用，
    #必须设为 on,如果用来进行下载等应用磁盘IO重负载应用，可设置为 off，以平衡磁盘与网络I/O处理速度，降低系统的uptime.
    sendfile        on;
    #将tcp_nopush和tcp_nodelay两个指令设置为on用于防止网络阻塞
    tcp_nopush      on;
    tcp_nodelay     on;
    #连接超时时间
    keepalive_timeout  65;
    #开启gzip压缩
    gzip  on;
    gzip_disable "MSIE [1-6]\.(?!.*SV1)";
    #设定请求缓冲
    client_header_buffer_size    1k;
    large_client_header_buffers  4 4k;
    include /etc/nginx/conf.d/*.conf;
    include /etc/nginx/sites-enabled/*;
    #设定负载均衡的服务器列表
    upstream mysvr {
        #weigth参数表示权值，权值越高被分配到的几率越大
        #本机上的Squid开启3128端口
        server 192.168.8.1:3128 weight=5;
        server 192.168.8.2:80  weight=1;
        server 192.168.8.3:80  weight=6;
    }
    server {
        #侦听端口,默认80
        listen       80;
        #定义使用www.xx.com访问
        server_name  www.xx.com;
        #设定本虚拟主机的访问日志
        access_log  logs/www.xx.com.access.log  main;
        #默认请求
        location / {
            root   /root;      #定义服务器的默认网站根目录位置
            index index.php index.html index.htm;   #定义首页索引文件的名称
            fastcgi_pass  www.xx.com;
            fastcgi_param  SCRIPT_FILENAME  $document_root/$fastcgi_script_name; 
            include /etc/nginx/fastcgi_params;
        }
        # 定义错误提示页面
        error_page   500 502 503 504 /50x.html;  
            location = /50x.html {
            root   /root;
        }
        #静态文件，nginx自己处理
        location ~ ^/(images|javascript|js|css|flash|media|static)/ {
            root /var/www/virtual/htdocs;
            #过期30天，静态文件不怎么更新，过期可以设大一点，如果频繁更新，则可以设置得小一点。
            expires 30d;
        }
        #PHP 脚本请求全部转发到 FastCGI处理. 使用FastCGI默认配置.
        location ~ \.php$ {
            root /root;
            fastcgi_pass 127.0.0.1:9000;
            fastcgi_index index.php;
            fastcgi_param SCRIPT_FILENAME /home/www/www$fastcgi_script_name;
            include fastcgi_params;
        }
        #设定查看Nginx状态的地址
        location /NginxStatus {
            stub_status            on;
            access_log              on;
            auth_basic              "NginxStatus";
            auth_basic_user_file  conf/htpasswd;
        }
        #禁止访问 .htxxx 文件
        location ~ /\.ht {
            deny all;
        }
    }
    #第一个虚拟服务器
    server {
        #侦听192.168.8.x的80端口
        listen       80;
        server_name  192.168.8.x;
        #对aspx后缀的进行负载均衡请求
        location ~ .*\.aspx$ {
            root   /root;#定义服务器的默认网站根目录位置
            index index.php index.html index.htm;#定义首页索引文件的名称
            proxy_pass  http://mysvr;#请求转向mysvr 定义的服务器列表
            #以下是一些反向代理的配置可删除.
            proxy_redirect off;
            #后端的Web服务器可以通过X-Forwarded-For获取用户真实IP
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            client_max_body_size 10m;    #允许客户端请求的最大单文件字节数
            client_body_buffer_size 128k;  #缓冲区代理缓冲用户端请求的最大字节数，
            proxy_connect_timeout 90;  #nginx跟后端服务器连接超时时间(代理连接超时)
            proxy_send_timeout 90;        #后端服务器数据回传时间(代理发送超时)
            proxy_read_timeout 90;         #连接成功后，后端服务器响应时间(代理接收超时)
            proxy_buffer_size 4k;             #设置代理服务器（nginx）保存用户头信息的缓冲区大小
            proxy_buffers 4 32k;               #proxy_buffers缓冲区，网页平均在32k以下的话，这样设置
            proxy_busy_buffers_size 64k;    #高负荷下缓冲大小（proxy_buffers*2）
            proxy_temp_file_write_size 64k;  #设定缓存文件夹大小，大于这个值，将从upstream服务器传
        }
    }
}
```

## 语法规则

1、配置文件由指令与指令块组成

2、每条指令以`;`结束，指令与参数间以空格分隔

3、指令块以`{}`大括号将多条指令组织在一起

4、include语句允许组合多个配置文件以提高可维护性

5、使用`#`添加注释，提高可读性

6、使用`$`符号使用变量

7、部分指令的参数支持正则表达式

## 全局块

全局快配置服务器整体运行的配置指令，比如工作进程数，运行的身份等

## events块

> TODO

## http块

与提供http服务相关的一些配置参数。例如：是否使用keepalive啊，是否使用gzip进行压缩等。

> TODO

## server块

http服务上支持若干虚拟主机。每个虚拟主机一个对应的server配置项，配置项里面包含该虚拟主机相关的配置。在提供mail服务的代理时，也可以建立若干server。每个server通过监听地址或端口来区分。

> TODO

### location块

http服务中，某些特定的URL对应的一系列配置项。

> TODO

## upstream块

上游服务

> TODO

# 常用配置

## 反向代理

### 一、反向代理百度

1、实现效果：浏览器访问虚拟机ip地址，跳转到百度页面

![image-20200223171407665](http://img.zhaojishun.cn/img/image-20200224143721921.png)

2、结构图

![image-20200224154803208](http://img.zhaojishun.cn/img/image-20200224144101419.png)

2、关键信息配置文件

```
server {
        listen       80;
        server_name  192.168.239.138;##本机ip，如果有域名解析过来可以填写域名
        location / {
            root   html;
			proxy_pass http://baidu.com;## 代理的网站
            index  index.html index.htm;
        }
    }
```

### 二、不同路径反代多个tomcat

1、实现效果：浏览器访问192.168.239.138/a，跳转到8080端口的tomcat1；访问192.168.239.138/b，跳转到8082端口的tomcat2；访问192.168.239.138/c，跳转到8083端口的tomcat3，根据访问路径不同，反代不同tomcat服务

![image-20200224144101419](http://img.zhaojishun.cn/img/image-20200224154803208.png)

2、结构图

![image-20200224155504329](http://img.zhaojishun.cn/img/image-20200224155504329.png)

2、准备工作：启动3个tomcat分别在8080、8082、8083端口，默认主页输出一句话，使用curl命令测试启动是否成功

![image-20200224151311923](http://img.zhaojishun.cn/img/image-20200224151311923.png)

3、关键信息配置文件

```
 upstream web1{
        server localhost:8080;
    }
	 upstream web2{
        server localhost:8082;
    }
	 upstream web3{
        server localhost:8083;
    }
	
    server {
        listen       80;
        server_name  192.168.239.138;
		
		location /a/ {
            proxy_pass http://web1/;
        }
		location /b/ {
            proxy_pass http://web2/;
        }
		location /c/ {
            proxy_pass http://web3/;
        }
    }
```

### 三、普通静态web服务器

```
server
{
    listen 80;
    server_name m.xxx.cn;
    index index.php index.html index.htm default.php default.htm default.html;
    root /www/wwwroot/m.xxx.cn/toolPage;
}
```

## 负载均衡

1、概念：负载均衡即是将负载分摊到不同的服务单元，既保证服务的可用性，又保证响应
足够快，给用户很好的体验。

2、分配方式

- 轮询（默认）每个请求按时间顺序逐一分配到不同的后端服务器，如果后端服务器down 掉，能自动剔除。

```
upstream server_pool{
server 192.168.5.21:80;
server 192.168.5.22:80;
}
```

- weight 权重默认为1,权重越高被分配的客户端越多，weight 和访问比率成正比，用于后端服务器性能不均的情况

  ```
  upstream server_pool{
  server 192.168.5.21 weight=10;
  server 192.168.5.22 weight=10;
  }
  ```

- 每个请求按访问ip 的hash 结果分配，这样每个访客固定访问一个后端服务器，可以解决session 的问题

```
upstream server_pool{
ip_hash;
server 192.168.5.21:80;
server 192.168.5.22:80;
}
```

3、关键配置文件

```
server {
        listen       80;
        server_name  192.168.239.138;
		
		location /a/ {
            proxy_pass http://server_pool/;
        }
    }
```

## 静态资源配置

1、由于tomcat可以处理静态资源，但效率不高，可以配合nginx实现动态请求用tomcat，静态资源使用nginx返回

2、关键配置文件

```
 server {
        listen       80;
        server_name  192.168.239.138;

        location / {
            root   html;
			proxy_pass http://tomcat;
        }
		location ~ .*\.(html|htm|gif|jpg|jpeg|bmp|png|ico|txt|js|css){
			root /data;
		}
    }
```

## 搭建文件服务器

1、有时候，团队需要归档一些数据或资料，那么文件服务器必不可少。使用 Nginx 可以非常快速便捷的搭建一个简易的文件服务。

2、效果

![image-20200224163141493](http://img.zhaojishun.cn/img/image-20200224163141493.png)

2、关键配置

```
autoindex on;# 显示目录
	autoindex_exact_size on;# 显示文件大小
	autoindex_localtime on;# 显示文件时间
	 server {
		charset      utf-8,gbk;
		listen       80 default_server;
		listen       [::]:80 default_server;
		server_name  _;
		root         /data;
	}
```