# awesome-env-config-cn
各种开发语言项目环境国内（中国国内加速镜像）配置教程和部分实践经验，包括github.com, nodejs，npm，nvm, yarn, java, maven, gradle, python, mysys2, elasticsearch, php等等，更多正在加入中

本项目地址：[https://github.com/mengyou658/awesome-env-config-cn](https://github.com/mengyou658/awesome-env-config-cn)

# TODO 待补充的
欢迎大家一起补充
* ruby
* pod
* ...
# **目录**
* [linux系统镜像源](#linux)
* [github镜像](#github)
* [nodejs镜像](#nodejs)
    * [nvm nodejs版本管理工具](#nvm) 
    * [yarn nodejs包管理工具](#yarn) 
    * [npm nodejs包管理工具](#npm) 
* [java JDK](#jdk)
    * [maven包管理](#maven)
    * [gradle包管理](#gradle)
* [python](#python)
    * [pip 包管理](#pip)
    * [miniAnaconda/anaconda包管理](#miniAnaconda)
* [elasticsearch镜像](#elasticsearch)
    * [kibana (elasticsearch管理工具)镜像](#kibana)
* [php镜像](#php)
    * [composer 包管理镜像](#composer)
* [msys2](#msys2)
    * [msys2 安装qt5](#msys2-qt5)
* [go](#go)
    * [GOPROXY解决go基础依赖无法下载得问题](#GOPROXY)
* [rust](#rust)
    * [cargo](#cargo)
* [github clone加速配置](#github-gitconfig)
    
---- 

## linux
* [**推荐使用阿里云镜像https://developer.aliyun.com/mirror/** 包括了各种镜像](https://developer.aliyun.com/mirror/)
    * [备用镜像，清华，**推荐https://mirrors.tuna.tsinghua.edu.cn/**：https://mirrors.tuna.tsinghua.edu.cn/](https://mirrors.tuna.tsinghua.edu.cn/)
    * [备用镜像，华为，**推荐https://mirrors.huaweicloud.com/**：https://mirrors.huaweicloud.com/](https://mirrors.huaweicloud.com/)
    1. 举例，ubuntu，访问[https://developer.aliyun.com/mirror/ubuntu?spm=a2c6h.13651102.0.0.3e221b11uHDvxz](https://developer.aliyun.com/mirror/ubuntu?spm=a2c6h.13651102.0.0.3e221b11uHDvxz)
    
## github
* [**推荐使用chrome插件** https://github.com/jadezi/github-accelerator/ 访问github对应的网站自动展示加速连接](https://github.com/jadezi/github-accelerator/)
    * 国内镜像源1，**推荐**：[https://hub.fastgit.xyz](https://hub.fastgit.xyz)
    * 国内镜像源1，这个目前不能直接访问，下载之类的不影响 **推荐**：[https://hub.fastgit.org](https://hub.fastgit.org)
    * 国内镜像源2：[https://github.com.cnpmjs.org 这个没有上面的快点](https://github.com.cnpmjs.org)

## nodejs
* nodejs 安装

    [镜像源：https://npmmirror.com/](https://npmmirror.com/) 
    
    [官方地址：nodejs.org](nodejs.org)
    
    * 直接下载安装（**推荐使用nvm管理nodejs版本自由切换**）：
    
        * 下载地址： [https://npm.taobao.org/mirrors/node](https://npm.taobao.org/mirrors/node) 选择对应的版本下载安装即可

* [nodejs 配置国内npm源，参考npm nodejs包管理工具配置](#npm)

## nvm
* linux或者mac

    [镜像源：https://hub.fastgit.xyz/nvm-sh/nvm](https://hub.fastgit.xyz/nvm-sh/nvm) 
    
    [官方地址：https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)
    
    * 安装
        * linux或者mac安装，镜像：
             ```bash
                curl -o- https://raw.fastgit.org/nvm-sh/nvm/master/install.sh | sed -e "s/raw.githubusercontent.com/raw.fastgit.org/g" | sed -e "s/github.com/hub.fastgit.org/g" | bash
                或者
                wget -qO- https://raw.fastgit.org/nvm-sh/nvm/master/install.sh | sed -e "s/raw.githubusercontent.com/raw.fastgit.org/g" | sed -e "s/github.com/hub.fastgit.org/g" | bash
             ```
        * linux或者mac安装，官方：
             ```bash
                curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
                或者
                wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
             ```
    * 配置国内源
        * 设置环境变量：NVM_NODEJS_ORG_MIRROR，bash编辑~/.bashrc，zsh编辑~/.zshrc
        ```bash
            export NVM_NODEJS_ORG_MIRROR=https://npm.taobao.org/mirrors/node
        ```
    
* windows 

    [镜像源：https://hub.fastgit.org/coreybutler/nvm-windows](https://hub.fastgit.org/coreybutler/nvm-windows) 
    
    [官方推荐地址：https://github.com/coreybutler/nvm-windows](https://github.com/coreybutler/nvm-windows)
    
    * 安装
        * 镜像：
             [https://hub.fastgit.org/coreybutler/nvm-windows/releases 下载最新的版本](https://hub.fastgit.org/coreybutler/nvm-windows/releases)
        * 官方：
             [https://github.com/coreybutler/nvm-windows/releases/ 下载最新的版本](https://github.com/coreybutler/nvm-windows/releases/)
    
    * 配置国内源
        * 设置
        ```cmd
            nvm node_mirror https://npm.taobao.org/mirrors/node
            nvm npm_mirror https://npm.taobao.org/mirrors/npm/
        ```
    
## yarn
* yarn 安装

    [官方地址：https://yarnpkg.com/](https://yarnpkg.com/)

    * 需要首先安装[nodejs](#nodejs)
    * 然后使用npm安装yarn或者更新
        ```cmd
        npm i -g yarn 
        或者
        npm install -g yarn 
       ```
* 配置国内源
    ```cmd
    yarn config set registry https://registry.npmmirror.com
    ```

## npm 

* npm 默认安装nodejs后就已经有了，使用以下命令查看
    ```cmd
    npm -v
    ```
* npm更新，一下不适用于nvm安装的node
    ```cmd
    npm i -g npm 
    ```
* 配置国内源，最简单的一种方式，自动配置淘宝源中多个配置
    ```cmd
    npm install -g --registry=https://registry.npmmirror.com mirror-config-china
    ```
## jdk
* java jdk 安装
    * [华为镜像，oracle的jdk有商业版权，没有最新版本下载 https://repo.huaweicloud.com/java/jdk/](https://repo.huaweicloud.com/java/jdk/) 
    * [官方下载速度不慢，目前需要注册登录oracle账号才能下载(百度搜索：jdk下载账号) https://www.oracle.com/cn/java/](https://www.oracle.com/cn/java/) 
    * [openjdk 镜像下载有很很多，比如清华 https://mirrors.tuna.tsinghua.edu.cn/AdoptOpenJDK](https://mirrors.tuna.tsinghua.edu.cn/AdoptOpenJDK)
* 配置现在一般都不需要配置

## maven
* [maven安装，apache比较良心，下载相关的基本都自带镜像 http://maven.apache.org/download.cgi](http://maven.apache.org/download.cgi)
    
    * [在此页面下载，默认自动选择最快的镜像 http://maven.apache.org/download.cgi](http://maven.apache.org/download.cgi)
    
* 配置国内源
    * [打开 maven 的配置文件（ windows 机器一般在 maven 安装目录的 conf/settings.xml 或者用户目录下.m2/setting.xml ），在<mirrors></mirrors>标签中添加 mirror 子节点, https://maven.aliyun.com/mvn/guide](https://maven.aliyun.com/mvn/guide)
    ```xml
    <mirror>
      <id>alimaven</id>
      <name>aliyun maven</name>
      <url>https://maven.aliyun.com/repository/public</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>jcenter</id>
      <name>jcenter</name>
      <url>https://maven.aliyun.com/repository/central</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>google</id>
      <name>google</name>
      <url>https://maven.aliyun.com/repository/google</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>spring</id>
      <name>aliyun maven spring</name>
      <url>https://maven.aliyun.com/repository/spring</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>spring-plugin</id>
      <name>aliyun maven spring-plugin</name>
      <url>https://maven.aliyun.com/repository/spring-plugin</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>gradle-plugin</id>
      <name>aliyun maven gradle-plugin</name>
      <url>https://maven.aliyun.com/repository/gradle-plugin</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>grails-core</id>
      <name>aliyun maven grails-core</name>
      <url>https://maven.aliyun.com/repository/grails-core</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    <mirror>
      <id>apache snapshots</id>
      <name>aliyun maven apache snapshots</name>
      <url>https://maven.aliyun.com/repository/apache-snapshots</url>
      <mirrorOf>central</mirrorOf>
    </mirror>

    ```
## gradle 
* gradle 安装 

    * [镜像：https://mirrors.cloud.tencent.com/gradle/](https://mirrors.cloud.tencent.com/gradle/)
      [感谢@oakfire提供](https://github.com/oakfire)
    * [官网 https://services.gradle.org/distributions/](https://services.gradle.org/distributions/)
* gradle 配置
    
    终极配置，在用户目录下~/.gradle/目录下增加init.gradle文件，内容如下
    ```groovy
     allprojects {
     	buildscript {
     		repositories {
     			mavenLocal()
     			def NEXUS_URL = 'https://maven.aliyun.com/repository/public'
     			def jcenter_URL = 'https://maven.aliyun.com/repository/jcenter'
     			def m2_URL = 'https://maven.aliyun.com/repository/gradle-plugin'
     			def spring_plugin_URL = 'https://maven.aliyun.com/repository/spring-plugin'
     			def spring_URL = 'https://maven.aliyun.com/repository/spring'
     			def GOOGLE_URL = 'https://maven.aliyun.com/repository/google'
     			all { ArtifactRepository repo ->
     				if(repo instanceof MavenArtifactRepository){
     					def url = repo.url.toString()
     					if (url.startsWith('https://repo1.maven.org/maven2') || url.startsWith('https://jcenter.bintray.com') || 		url.startsWith('http://mirrors.ibiblio.org')) {
     						project.logger.lifecycle "Repository ${repo.url} replaced by $jcenter_URL."
     						remove repo
     					} else if (url.startsWith('https://plugins.gradle.org/m2/')) {
     						project.logger.lifecycle "Repository ${repo.url} replaced by $m2_URL."
     						remove repo
     					} else if (url.startsWith('http://repo.spring.io/libs-milestone/')) {
     						project.logger.lifecycle "Repository ${repo.url} replaced by $spring_URL."
     						remove repo
     					} else if (url.startsWith('http://repo.spring.io/plugins-release/')) {
     						project.logger.lifecycle "Repository ${repo.url} replaced by $spring_plugin_URL."
     						remove repo
                        // 这里是安卓相关下载的加速，本地没有出现下载慢的情况，所以这个就屏蔽了
     					//}else if (url.startsWith('https://dl.google.com/dl/android/maven2/')) {
     					//	project.logger.lifecycle "Repository ${repo.url} replaced by $GOOGLE_URL."
     					//	println("buildscript ${repo.url} replaced by $GOOGLE_URL.")
     					//	remove repo
     					}
     				}
     			}
     			
     			maven { url 'https://maven.aliyun.com/repository/public' }
     			maven { url 'https://maven.aliyun.com/repository/spring' }
     			maven { url 'https://maven.aliyun.com/repository/spring-plugin' }
     			maven { url "https://maven.aliyun.com/repository/grails-core" }
     			maven { url "https://maven.aliyun.com/repository/apache-snapshots" }
     			maven { url "https://maven.aliyun.com/repository/gradle-plugin" }
     			maven { url 'https://maven.aliyun.com/repository/google' }
     			jcenter {
     				url jcenter_URL
     			}
     			maven {
     				url NEXUS_URL
     			}
     		}
     	
     	}
         repositories {
             mavenLocal()
     		def NEXUS_URL = 'https://maven.aliyun.com/repository/public'
     		def jcenter_URL = 'https://maven.aliyun.com/repository/jcenter'
     		def m2_URL = 'https://maven.aliyun.com/repository/gradle-plugin'
     		def spring_plugin_URL = 'https://maven.aliyun.com/repository/spring-plugin'
     		def spring_URL = 'https://maven.aliyun.com/repository/spring'
     		def GOOGLE_URL = 'https://maven.aliyun.com/repository/google'
             all { ArtifactRepository repo ->
                 if(repo instanceof MavenArtifactRepository){
                     def url = repo.url.toString()
                     if (url.startsWith('https://repo1.maven.org/maven2') || url.startsWith('https://jcenter.bintray.com') || 		url.startsWith('http://mirrors.ibiblio.org')) {
                         project.logger.lifecycle "Repository ${repo.url} replaced by $jcenter_URL."
                         remove repo
                     } else if (url.startsWith('https://plugins.gradle.org/m2/')) {
                         project.logger.lifecycle "Repository ${repo.url} replaced by $m2_URL."
                         remove repo
                     } else if (url.startsWith('http://repo.spring.io/libs-milestone/')) {
                         project.logger.lifecycle "Repository ${repo.url} replaced by $spring_URL."
                         remove repo
                     } else if (url.startsWith('http://repo.spring.io/plugins-release/')) {
                         project.logger.lifecycle "Repository ${repo.url} replaced by $spring_plugin_URL."
                         remove repo
                    // 这里是安卓相关下载的加速，本地没有出现下载慢的情况，所以这个就屏蔽了
                    //}else if (url.startsWith('https://dl.google.com/dl/android/maven2/')) {
     				//	project.logger.lifecycle "Repository ${repo.url} replaced by $GOOGLE_URL."
     				//	println("buildscript ${repo.url} replaced by $GOOGLE_URL.")
     				//	remove repo
     				}
                 }
             }
             
     		maven { url 'https://maven.aliyun.com/repository/public' }
             maven { url 'https://maven.aliyun.com/repository/spring' }
             maven { url 'https://maven.aliyun.com/repository/spring-plugin' }
     		maven { url "https://maven.aliyun.com/repository/grails-core" }
             maven { url "https://maven.aliyun.com/repository/apache-snapshots" }
             maven { url "https://maven.aliyun.com/repository/gradle-plugin" }
     		maven { url 'https://maven.aliyun.com/repository/google' }
             jcenter {
     			url jcenter_URL
     		}
     		maven {
     			url NEXUS_URL
     		}
         }
     }

    ```
  
## python
* python 安装
    * windows 系统安装，直接下载安装包
        * [阿里云镜像，https://npm.taobao.org/mirrors/python/](https://npm.taobao.org/mirrors/python/) 
        * [官方下载，https://www.python.org/downloads/](https://www.python.org/downloads/) 
    * linux 系统默认自带python，需要单独安装新版本，linux系统镜像配置请参考[linux系统镜像源](#linux)
        * ubuntu
        ```bash
            sudo apt-get update
            sudo apt-cache search python3*
            sudo apt-get install python3.8 # python3.5 python3.6 python3.7 等，python3.8是当前书写的时候最新稳定版本
        ```
        * centos
        ```bash
            sudo yum install epel-release -y
            sudo yum -y update
            sudo yum list python3* # 使用此命令查看当前支持的python3版本
            sudo yum install python37 # python35 python36 python37 等，python38是当前书写的时候最新稳定版本
        ```
      
## pip
* pip 安装 python 安装成功后，默认自带pip
* [阿里云镜像说明，https://developer.aliyun.com/mirror/pypi](https://developer.aliyun.com/mirror/pypi) 
    * windows 下配置
        ```cmd
        mkdir %USERPROFILE%\.pip\
        start %USERPROFILE%\.pip\
        ``` 
        * 在这个目录下创建pip.conf文件（推荐使用notepad++）
        写入内容如下：
        ``` 
        [global]
        index-url = https://mirrors.aliyun.com/pypi/simple/
        
        [install]
        trusted-host=mirrors.aliyun.com
        ``` 
    * linux 
        ```bash
        mkdir -p ~/.pip
        # ubuntu 桌面下可以使用 gedit ~/.pip/pip.conf
        # vi 入门可以参考 https://github.com/wsdjeg/vim-galore-zh_cn
        vi ~/.pip/pip.conf
        ```
        写入内容如下：
        ``` 
        [global]
        index-url = https://mirrors.aliyun.com/pypi/simple/
        
        [install]
        trusted-host=mirrors.aliyun.com
        ``` 
      
## miniAnaconda
* [(一般使用miniAnaconda，anaconda占用空间大，土豪可以直接忽略)清华镜像源，这里包括了anaconda的安装配置说明，https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/](https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/) 
* 安装 https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/ 下载对应的文件执行
    * windows安装
        下载最新的exe文件安装
    * linux安装
        ```bash
        wget https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-py38_4.8.3-Linux-x86_64.sh
        sh Miniconda3-py38_4.8.3-Linux-x86_64.sh.sh
        ```
* 配置镜像
    * windows 下配置
        ```cmd
        conda config --set show_channel_urls yes
        start %USERPROFILE%\
        ``` 
        * 在这个目录下编辑.condarc文件（推荐使用notepad++编辑，如果看不到这个文件，请打开windows系统的隐藏文件选项）
        写入内容如下：
        ``` 
        channels:
          - defaults
        show_channel_urls: true
        channel_alias: https://mirrors.tuna.tsinghua.edu.cn/anaconda
        default_channels:
          - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
          - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
          - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
          - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/pro
          - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
        custom_channels:
          conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
          msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
          bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
          menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
          pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
          simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
        ``` 
    * linux 
        ```bash
        conda config --set show_channel_urls yes
        # ubuntu 桌面下可以使用 gedit ~/.condarc
        # vi 入门可以参考 https://github.com/wsdjeg/vim-galore-zh_cn
        vi ~/.condarc
        ```
        写入内容如下：
        ``` 
        channels:
          - defaults
        show_channel_urls: true
        channel_alias: https://mirrors.tuna.tsinghua.edu.cn/anaconda
        default_channels:
          - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
          - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
          - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
          - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/pro
          - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
        custom_channels:
          conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
          msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
          bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
          menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
          pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
          simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
        ``` 

## elasticsearch
* elasticsearch 安装
    * [华为云镜像，https://mirrors.huaweicloud.com/elasticsearch/](https://mirrors.huaweicloud.com/elasticsearch/) 
    * [官方下载，https://www.elastic.co/cn/downloads/elasticsearch](https://www.elastic.co/cn/downloads/elasticsearch) 

## kibana
* kibana (elasticsearch管理工具) 安装，需要下载与elasticsearch版本一致
    * [华为云镜像，https://mirrors.huaweicloud.com/kibana/](https://mirrors.huaweicloud.com/kibana/) 
    * [官方下载，https://elastic.co/downloads/kibana](https://elastic.co/downloads/kibana) 

## php
* [官方下载速度不慢，https://downloads.php.net/](https://downloads.php.net/)
* php 安装
    * windows下
        * [一般使用phpstudy，简单方便 https://m.xp.cn/](https://m.xp.cn/)
    * linux 下
        * [一键安装脚本 https://lnmp.org/install.html](https://lnmp.org/install.html) 
        * [阿里云参考教程，https://help.aliyun.com/document_detail/97251.html](https://help.aliyun.com/document_detail/97251.html) 

## composer
* [安装和配置参考，https://pkg.phpcomposer.com/#how-to-install-composer](https://pkg.phpcomposer.com/#how-to-install-composer)
* [国内镜像用法参考，https://pkg.phpcomposer.com/#how-to-use-packagist-mirror](https://pkg.phpcomposer.com/#how-to-use-packagist-mirror)

## msys2
* [msys2 安装，清华镜像，https://mirror.tuna.tsinghua.edu.cn/help/msys2/](https://mirror.tuna.tsinghua.edu.cn/help/msys2/)

## msys2-qt5
* [msys2 安装，清华镜像，https://mirror.tuna.tsinghua.edu.cn/help/msys2/](https://mirror.tuna.tsinghua.edu.cn/help/msys2/)
* 配置镜像源
    1. 修改C:\msys64\etc\pacman.d（默认安装在c盘下面）下面得mirrorlist.*文件，把清华镜像相关得移动到最前面
    1. 安装
    ```bash
    # 更新系统包
    pacman -Syu
    # 基础包
    pacman -S --needed base-devel mingw-w64-x86_64-toolchain mingw-w64-x86_64-cmake bash wget p7zip pacman pacman-mirrors msys2-runtime
    # qt5
    pacman -S  mingw-w64-x86_64-clang mingw-w64-x86_64-clang-tools-extra  mingw-w64-x86_64-clang-analyzer mingw-w64-x86_64-qt5  mingw-w64-x86_64-qt-creator 
    ```


## go
* [go 安装，goproxy.io七牛镜像，https://gomirrors.org/](https://gomirrors.org/)

## GOPROXY
* [goproxy.io七牛镜像](https://goproxy.io)
* 环境设置
1. windows对应的设置环境变量即可（也可以自己手动设置环境变量，以下需要管理员运行命令行）
    ```cmd
    setx /m GOPROXY https://goproxy.io,direct
    setx /m GO111MODULE auto
    ```
1. linux 环境 编辑~/.bashrc（bash）或者~/.zshrc（zsh)
    ```bash
    export GOPROXY=https://goproxy.io,direct
    export GO111MODULE=auto
    ```

## rust
* [rust 清华镜像 https://mirrors.tuna.tsinghua.edu.cn/rustup/](https://mirrors.tuna.tsinghua.edu.cn/rustup/)
    1. windows 下安装
        1. [下载 https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe](https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe)
        1. 设置环境变量(请以管理员运行)
           ```cmd
              setx /m RUSTUP_DIST_SERVER https://mirrors.tuna.tsinghua.edu.cn/rustup
              setx /m RUSTUP_UPDATE_ROOT https://mirrors.tuna.tsinghua.edu.cn/rustup/rustup
            ```
        1. 执行rustup-init.exe安装
    1. linux 下安装
        1. 设置环境变量 编辑~/.bashrc（bash）或者~/.zshrc（zsh)
           ```bash
              export RUSTUP_DIST_SERVER=https://mirrors.tuna.tsinghua.edu.cn/rustup
              export export RUSTUP_UPDATE_ROOT=https://mirrors.tuna.tsinghua.edu.cn/rustup/rustup
            ```
        1. 安装
            ```bash
                curl https://sh.rustup.rs -sSf | sh
                # 这里也可以下载对应的数据，直接安装 https://mirrors.ustc.edu.cn/rust-static/rustup/dist/
                # wget https://mirrors.ustc.edu.cn/rust-static/rustup/dist/x86_64-apple-darwin/rustup-init
                # ./rustup-init
            ```
* [rust 官方下载速度还可以 https://www.rust-lang.org/](https://www.rust-lang.org/)
    1. windows 下安装
        1. [下载 https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe](https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe)
        1. 执行rustup-init.exe安装
    1. linux 下安装
        1. linux安装
            ```bash
              curl https://sh.rustup.rs -sSf | sh
            ```
        1. wsl安装
            ```bash
              curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
            ```

## cargo
* 环境设置
1. windows 到 %USERPROFILE%\.cargo 当前用户的.cargo目录下，新建或者修改config，内容如下
```
[source.crates-io]
registry = "https://github.com/rust-lang/crates.io-index"
# 替换成你偏好的镜像源
replace-with = 'tuna'

# 清华大学
[source.tuna]
registry = "https://mirrors.tuna.tsinghua.edu.cn/git/crates.io-index.git"

# 中国科学技术大学
[source.ustc]
registry = "git://mirrors.ustc.edu.cn/crates.io-index"

# 上海交通大学
[source.sjtu]
registry = "https://mirrors.sjtug.sjtu.edu.cn/git/crates.io-index"

# rustcc社区
[source.rustcc]
registry = "git://crates.rustcc.cn/crates.io-index"
```
1. linux 环境 编辑`vi ~/.cargo/config`
```
[source.crates-io]
registry = "https://github.com/rust-lang/crates.io-index"
# 替换成你偏好的镜像源
replace-with = 'tuna'

# 清华大学
[source.tuna]
registry = "https://mirrors.tuna.tsinghua.edu.cn/git/crates.io-index.git"

# 中国科学技术大学
[source.ustc]
registry = "git://mirrors.ustc.edu.cn/crates.io-index"

# 上海交通大学
[source.sjtu]
registry = "https://mirrors.sjtug.sjtu.edu.cn/git/crates.io-index"

# rustcc社区
[source.rustcc]
registry = "git://crates.rustcc.cn/crates.io-index"
```

## github-gitconfig
备注：github clone的时候使用git方式下载基本不出问题
* 环境设置
1. windows 到 %USERPROFILE%\.gitconfig 当前用户的.gitconfig文件，内容如下
```
[url "git@github.com:"]
	insteadOf = https://github.com/
```
