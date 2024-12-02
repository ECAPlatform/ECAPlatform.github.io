# IDEA导入项目





# IDEA导入前后端项目

> Version: 3.4.1+ 版本

```
 JeecgBoot采用前后分离架构，官方推荐前后端都用IDEA
```

- [IDEA导入前后端项目](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043873#IDEA_0)

- - [第一部分： 前端项目导入](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043873#__9)

  - - [一、安装前端环境](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043873#_10)
    - [二、导入Vue2前端项目](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043873#Vue2_13)
    - [三、前端构建运行](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043873#_19)

  - [第二部分： 后端项目导入](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043873#__26)

  - - [一、安装jdk8、Maven、Redis、Mysql](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043873#jdk8MavenRedisMysql_28)
    - [二、导入JAVA项目&启动](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043873#JAVA_30)

## 第一部分： 前端项目导入

### 一、安装前端环境

安装nodejs、yarn、IDEA，安装方法参照 [【开发环境安装】](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043872)

### 二、导入Vue2前端项目

（1）前端工程 ant-design-vue-jeecg
 （2）IDEA 打开项目
![img](https://img.kancloud.cn/75/47/7547d9a04f3a71cf48fa9939eb5e6862_650x611.png)

### 三、前端构建运行

（1）选中`package.json`右键显示`npm`命令
![img](https://img.kancloud.cn/3a/6c/3a6c92b0571c9627373f98ad7e560579_549x414.png)
 （2）通过命令 `yarn install`或者快捷 `pre`下载依赖，点击`serve` 启动项目
![img](https://img.kancloud.cn/91/c9/91c9e5d1edf4c50f92bf3084fad4a36e_652x691.png)
 （3）点击`serve` 启动项目

## 第二部分： 后端项目导入

### 一、安装jdk8、Maven、Redis、Mysql

```
 此部分属于java基础不讲，不会的百度吧！！
```

### 二、导入JAVA项目&启动

![img](https://img.kancloud.cn/ea/8b/ea8b8840938da5f8295b267af21d9af1_1397x829.png)

- 通过右侧父POM进行`install`（下载依赖和打包）
  ![img](https://img.kancloud.cn/b8/d4/b8d47c743e978c06265844393dfa7257_322x400.png)
- 右键执行类`jeecg-module-system/jeecg-system-start/src/main/java/org/jeecg/JeecgSystemApplication.java` 启动项目
- 后台项目启动具体配置，[参考此文档](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043874)

上一篇：[开发环境安装](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043872)下一篇：[通过IDEA启动项目](https://www.kancloud.cn/zhangdaiscott/jeecg-boot/2043874)