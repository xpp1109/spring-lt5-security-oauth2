> # 前言  

​	Oauth2授权是项目中使用很多的协议，在三方授权中有这很大的应用。

​	spring 官方宣布在spring-security5以后删除掉Authorization Server相关功能，官方推荐使用第三方oauth2服务器，例如keycloak。作为spring的忠实舔狗，我跟很多开发者一样对spring的这个宣布不能认同，spring 迫于对广大开发者强烈不满和迫切需求，觉得另开一个项目（Spring Authorization Server）. 时间过去很久了。社区一直在开发中。

​	在开发过程中社区将jar包上传到maven central，例如0.1.0-0.1.2版本，但是都未明文说明可以使用到生产环境。

​	近期spring 官方发布了几个通知：

* 2021年8月17日，通知：Spring Authorization Server迁移到spring projects

​	![image-20210825093410598](https://raw.githubusercontent.com/xpp1109/images/main/uPic/image-20210825093410598.png)

* 2021年8月19日，通知Spring Authorization Server 生产环境可用。（其实这几天官方的通知有变化，比如先发的文档，上面未写maven central上的jar地址。也可以理解，事情要一步一步做的嘛😁）

  ![image-20210825093554682](https://raw.githubusercontent.com/xpp1109/images/main/uPic/image-20210825093554682.png)

  看到该通知后，想尝试下。于是进入仓库地址（https://github.com/spring-projects/spring-authorization-server），未发现有使用文档，只有源码和使用示例。

  ​	因此有些抵触，没有文档使用难度较大，无法深入理解开发者思想。所以想再等等。

  ​	此时想起以前的oauth2实现方案，想做个复习，所以想写个demo。记录下来。也给其他学者一个参考。因此写下此demo。

  *之后我会使用Spring Authorization Server* 依赖，再次实现跟本demo一样的例子，敬请关注。

> # 什么是Oauth2.0

​	本文不作赘述，网上文章较多。推荐几个，https://www.ruanyifeng.com/blog/2019/04/oauth-grant-types.html， https://oauth.net/2/ 。https://zhuanlan.zhihu.com/p/84670338。



> # 使用Spring Security和Spring Security Oauth2依赖实现

* 说明

  spring Boot： 2.3.4.RELEASE

  spring-Security-oauth2：2.5.1.RELEASE

  jdk: 1.8

  开发工具: IDEA

  包管理工具：MAVEN

* 项目结构

  
