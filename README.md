##  项目介绍

<div align="center">

[![GitHub stars](https://img.shields.io/github/stars/xddcode/free-fs?logo=github)](https://github.com/xddcode/free-fs/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/xddcode/free-fs?logo=github)](https://github.com/xddcode/free-fs/network)
[![star](https://gitee.com/xddcode/free-fs/badge/star.svg?theme=dark)](https://gitee.com/xddcode/free-fs/stargazers)
[![fork](https://gitee.com/xddcode/free-fs/badge/fork.svg?theme=dark)](https://gitee.com/xddcode/free-fs/members)
[![AUR](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg)](https://gitee.com/xddcode/free-fs/blob/master/LICENSE)
</div>

!> Free-Fs 开源文件管理系统：基于 SpringBoot2.x + MyBatisPlus + MySQL + Shiro+ Layui 等搭配七牛云，阿里云OSS实现的云存储管理系统。包含文件上传、删除、预览、云资源列表查询、下载、文件移动、重命名、目录管理、登录、注册、以及权限控制等功能。

**源码地址：**

+ [Gitee](https://www.gitee.com/dh_free/free-fs)
+ [Github](https://www.github.com/dh-free/free-fs)

**开发文档：**
[文档](https://xddcode.github.io/fs-doc/)

**在线预览：**
[https://fs.elites.chat](https://fs.elites.chat)

**内置账号：**

|     |   账号  |   密码|   权限  |
|---  |--- | --- | --- |
|  管理员   |  admin   |  admin   | 所有权限  |
|  普通用户   |  fs|  fs   | 查看，复制，下载，上传 |

##  快速了解
### 主要特性
- 整合阿里云、七牛云两个当下火热的云存储，对存储管理操作快速便捷。
- 代码简化整洁，适合二次开发。
- 利用mybatisPlus的多租户特性，只需更改一个配置就能动态切换当前系统使用的存储类型（本地Local、七牛云还是阿里云）。
- 项目前后端没有分离，降低上手开发难度。
- 全局异常统一拦截和处理，避免繁琐的判断。
- 自定义权限注解与匿名接口注解，可快速对接口拦截与放行。
- 移除内嵌Tomcat容器，使用Undertow来提高性能。

### 主要功能
- 用户管理：实现用户登录，与注册。
- 文件管理：实现对文件上传，下载，查看，重命名，移动，删除等管理。
- 权限控制：不同角色登录的用户，对文件的操作权限不同。
- 目录管理：文件夹目录管理，重命名，移动，删除等。

### 项目结构

```
- sql                         项目数据库文件
- src
  - main
    - java
    - com.free.fs
      - common                公共模块
        - annotation          自定义注解
        - aop                 自定义切面
        - config              系统基本配置，本地资源映射、sa拦截器注册，跨域配置等
        - constant            系统常量
        - domian              系统实体类
        - exception           全局异常处理和自定义异常
        - properties          资源读取类
        - template            文件上传模板类
        - utils               系统工具类
      - controller            控制层
      - mapper                mapper接口层
      - model                 实体模型层
      - service               业务接口
        -impl                 业务接口实现
      - xxApplication.java    启动类
  - resources
    - mapper                  mybatis mapper.xml
    - static                  静态资源包存放js css 第三方插件
    - templates               静态页面 html
    - application.yml         配置文件
    - application-dev.yml     开发环境配置
    - application-prod.yml    生产环境配置
```

## 快速开始

### 系统设计
![](https://dh_free.gitee.io/images/img/1616399886.png "1616399886.png")

### 项目技术栈
后端：

- Spring Boot 2.6.6
- orm: MyBatis Plus 3.5.1
- 数据库：MySQL 8.0+
- 权限安全控制：Sa-Token
- 本地缓存：Ehcache
- 文件上传：本地Local、七牛云、阿里云OSS

前端：

- Thymeleaf
- Layui v2.5.5
- Jquery
- Ajax

### 所需环境
- 操作系统：Windows 10
- 构建工具：Maven
- 开发工具：Intellij IDEA
- 应用服务器：Apache Tomcat
- 接口测试工具：Postman
- 压力测试工具：Apache JMeter
- 版本控制工具：Gitee
- Java 版本：8
- 七牛云存储
- 阿里云存储


```
1. JDK：1.8+ 
安装教程：https://www.runoob.com/java/java-environment-setup.html
2. Maven 3.0+
安装教程：https://www.runoob.com/maven/maven-setup.html
3. MYSQL 5.7+
安装教程：https://www.runoob.com/mysql/mysql-install.html
```


### 开发准备
!> 为了便于项目开发，你可能还需以下准备。

+ 1. idea安装lombok插件，否则项目会报错。lombok主要工作是简化代码，节省不必要的时间。具体可以查看：[lombok](https://www.jianshu.com/p/2543c71a8e45)
+ 2. 了解MybatisPlus，本人比较懒，大多数sql都用mp代替，所以不熟悉mp的同学可能看不懂代码。具体可以查看：[MybatisPlus](https://mp.baomidou.com/)
+ 3. 项目是由Springboot开发，所以你还需要springboot的相关知识，具体可以查看：[Springboot](https://blog.csdn.net/tengshe789/article/details/81488477)
+ 4. 前端是由Layui+jquery实现，所以你需要去看看layui的部分基础和语法，具体可以查看：[Layui](https://www.layui.com/doc/)
+ 5. 认证授权是用Shiro实现，不妨也可以去看一看：[Shiro](https://blog.csdn.net/aimashi620/article/details/80880007)

### 运行项目
打开idea，导入git项目
![](https://dh_free.gitee.io/images/img/1.png "1.png")

输入我们的git地址：https://gitee.com/dh_free/free-fs.git
![](https://dh_free.gitee.io/images/img/2.png "2.png")

导入成功后，配置我们的本地maven地址
![](https://dh_free.gitee.io/images/img/3.png "3.png")

idea如果是2019之前的版本记得在配好maven后会弹出一个选择框，记得勾选：Enable Auto-Import 自动导入包，这样在每次修改pom.xml后idea会自动更新jar包。

等待项目开始下载依赖包，如果下载太慢，记得给自己的maven配置阿里镜像，找到自己maven安装目录conf/setting.xml,加入以下配置：

```
 <mirrors>
    <mirror>  
      <id>alimaven</id>  
      <name>aliyun maven</name>  
      <url>http://maven.aliyun.com/nexus/content/groups/public/</url>  
      <mirrorOf>central</mirrorOf>          
    </mirror> 
  </mirrors>
```

镜像配置好后，如果下载突然卡住了，则关掉idea后在重新打开，然后点击Reimport按钮重新拉取，如果不行多试几次：
![](https://dh_free.gitee.io/images/img/4.png "4.png")

等待全部插件和依赖下载完成，查看并设置项目的编码集：
![](https://dh_free.gitee.io/images/img/5.png "5.png")

查看并设置项目jdk，有时候不需要自己设置，但是偶尔会有问题，检查一下：打开file->Project Structure，一次查看并修改为jdk1.8：
![](https://dh_free.gitee.io/images/img/6.png "6.png")
![](https://dh_free.gitee.io/images/img/7.png "7.png")
![](https://dh_free.gitee.io/images/img/8.png "8.png")

!> 到此时我们开发工具环境就差不多了，然后下一步准备本项目的数据库

打开我们的Navicat等db工具，打开数据库，创建一个名字为 **free-fs** 的数据库并选好字符集：
![](https://dh_free.gitee.io/images/img/9.png "9.png")

导入我们的sql文件（文件在项目的sql文件夹内），点击开始按钮后开始导入数据库，导入成功后查看会生成我们的5张表：  
![](https://dh_free.gitee.io/images/img/11.png "11.png")
![](https://dh_free.gitee.io/images/img/10.png "10.png")
![](https://dh_free.gitee.io/images/img/12.png "12.png")

!> 到此时我们数据库准备完毕，最后修改项目的配置信息

找到配置文件application-dev.yml（这是开发环境的配置文件，application-pro.yml是生产环境，到时候自己部署的时候可以自由切换），修改数据库的连接信息改为自己的：
![](https://dh_free.gitee.io/images/img/13.png "13.png")

找到配置文件application.yml主配置文件，修改七牛云的配置为自己账号的配置：
![](https://dh_free.gitee.io/images/img/14.png "14.png")

- 没有七牛云的，自己可以查看[七牛云](http://)，自己去开通一个账号与云空间（免费的）。
