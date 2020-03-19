title: 编译Ubuntu/Debian固件
---

你可以使用[Fenix](https://github.com/khadas/fenix)脚本来编译Ubuntu/Debian固件。

### 设置本地编辑环境
```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install git make lsb-release qemu-user-static
```

### 下载Fenix脚本
下载Fenix脚本到本地路径，如:`~/project/`
```sh
$ mkdir ~/project/
$ cd ~/project/
$ git clone --depth 1 https://github.com/khadas/fenix
```

### 设置编译环境
你需要先设置Fenix编译环境，如：选择Khadas开发板型号、u-boot版本、linux版本、linux发行版、安装方式等等。
```sh
$ cd ~/project/fenix
$ source env/setenv.sh
```
### 开始编译完整固件
在设置好环境执行`make`就会开始编译，编译过程会用到`root`权限，会提示你要输入密码才能继续编译。
```sh
$ make
```

**提示：**如果是你第一次编译，那么时间会比较久，因为脚本会检测你的电脑的编译环境，可能会安装编译需要的一些软件包，同时还会从Khadas Github下载一些仓库（如：u-boot和linux）。

你也可以选择单独编译u-boot和内核。

### 编译U-boot
```
$ make uboot
```

### 编译U-boot debian包
```
$ make uboot-deb
```

### 编译内核
```
$ make kernel
```

### 编译内核debian包
```
$ make kernel-deb

### 编译GPU debian包
```
$ make gpu-deb
```

### 编译板级debian包
```
$ make board-deb
```

### 编译所有的debian包
```
$ make debs
```

### 获取帮助信息
通过执行`make help`来获取帮助信息。
```sh
$ make help
Fenix scripts help messages:
  all           - Create image according to environment.
  kernel        - Build linux kernel.
  uboot         - Build u-boot.
  uboot-deb     - Build u-boot debian package.
  kernel-deb    - Build linux debian package.
  board-deb     - Build board debian package.
  common-deb    - Build common debian package.
  desktop-deb   - Build desktop debian package.
  gpu-deb       - Build gpu debian package.
  debs          - Build all debian packages.
  image         - Pack update image.
  clean         - Cleanup.
  info          - Display current environment.
```

### 使用Docker编译
Fenix支持在Docker中编译，我们提供了一个`Ubuntu 18.04`的Docker环境，你可以在里面编译所有的固件。

#### 安装Docker
这里提供`Ubuntu 16.04`或新版本的Docker安装方法。

卸载旧版本Docker：
```
$ sudo apt-get remove docker docker-engine docker.io
```

安装必要的软件包：
```
$ sudo apt-get update
$ sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
$ curl -fsSL https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
```

添加Docker源：
```
$ sudo add-apt-repository \
    "deb [arch=amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu \
    $(lsb_release -cs) \
    stable"
```

安装Docker:
```
$ sudo apt-get update
$ sudo apt-get install docker-ce
```
启动Docker:
```
$ sudo systemctl enable docker
$ sudo systemctl start docker
```
添加Docker用户组：
```
$ sudo groupadd docker
$ sudo usermod -aG docker $USER
```
*注意: 必须注销或重启系统才会生效。*

#### 检查Docker
```
$ docker run hello-world
```

如果你看到如下信息输出说明Docker安装成功：
```
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
ca4f61b1923c: Pull complete
Digest: sha256:be0cd392e45be79ffeffa6b05338b98ebb16c87b255f48e297ec7f98e123905c
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://cloud.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/engine/userguide/
```
#### 在Docker中运行Fenix
编译Docker镜像：
```
$ cd ~/project/fenix
$ docker build -t fenix .
```

进入Docker环境：
```
$ docker run -it --name fenix -v $(pwd):/home/khadas/fenix -v /etc/localtime:/etc/localtime:ro -v /etc/timezone:/etc/timezone:ro --privileged --device=/dev/loop0:/dev/loop0 --cap-add SYS_ADMIN fenix
```
现在已经在Docker容器里面了，可以开始编译了：
```
khadas@919cab43f66d:~/fenix$ source env/setenv.sh
khadas@919cab43f66d:~/fenix$ make
```

下一次可以用如下命令启动Docker：

```
$ docker start fenix
$ docker exec -ti fenix bash
```

### 参考
[Docker](https://www.docker.com/)


