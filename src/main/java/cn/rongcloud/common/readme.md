### SealDemo-Common 模块说明

> SealDemo-Common 提供通用 IM 交互封装、SMS 交互封装、JWT 鉴权、通用工具类等功能，其他 Demo Server 可以直接将该模块作为 git 子模块引入到项目中，减少非必要工作量。

#### 引入指南

**1、需要将以下依赖添加至项目 pom.xml 文件中**

```
  <parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.3.0.RELEASE</version>
    <relativePath/> <!-- lookup parent from repository -->
  </parent>
  
  <dependency>
      <groupId>io.jsonwebtoken</groupId>
      <artifactId>jjwt</artifactId>
      <version>0.7.0</version>
  </dependency>
  
  <dependency>
      <groupId>org.apache.directory.studio</groupId>
      <artifactId>org.apache.commons.codec</artifactId>
      <version>1.8</version>
  </dependency>
  
  <dependency>
      <groupId>com.google.code.gson</groupId>
      <artifactId>gson</artifactId>
      <version>2.8.6</version>
  </dependency>
  
  <dependency>
      <groupId>org.projectlombok</groupId>
      <artifactId>lombok</artifactId>
      <version>1.16.10</version>
  </dependency>
  
```

**2、需要将以下配置添加至项目 application.xml 文件中**

```
jwt:
  secret: "ay9pL#$SealMic"
  ttlInMilliSec: -1

## im config
im:
  appKey: x18ywvqfxck1c
  secret: OWRMmH9sFT
  host: http://api-cn.ronghub.com
sms:
  appKey: n19jmcy59f1q9
  secret: CuhqdZMeuLsKj
  host: http://api.sms.ronghub.com
```

**3、将 SealDemo-Common 引入到 DemoServer 项目中**

```
git submodule add <url> <path>

```
其中，url为子模块的路径，path为该子模块存储的目录路径。示例, 在项目根目录下执行如下命令:
```
git submodule add ssh://git@pha.rongcloud.net:2222/diffusion/127/sealdemo-common.git src/main/java/cn/rongcloud/common
```

执行成功后，git status会看到项目中修改了.gitmodules，并增加了一个新文件（为刚刚添加的路径。

`git diff --cached` 查看修改内容可以看到增加了子模块，并且新文件下为子模块的提交hash摘要

`git commit` 提交即完成子模块的添加




