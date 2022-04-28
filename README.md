
<p align="center">
	<img src="https://img.shields.io/badge/JDK-1.8+-orange">
	<img src="https://img.shields.io/badge/SpringBoot-2.2.7.RELEASE-brightgreen">
	<img src="https://img.shields.io/badge/MyBatis-3.5.5-red">
	<img src="https://img.shields.io/badge/Vue-2.6.11-brightgreen">
	<img src="https://img.shields.io/badge/license-MIT-blue">
	<img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FNaccl%2FNBlog&count_bg=%2344CC11&title_bg=%23555555&icon=notist.svg&icon_color=%231296DB&title=hits&edge_flat=false">
</p>



## 简介

说明：原始项目地址：https://github.com/Naccl/NBlog, 在原来的基础上增加docker/k8s配置，并且前端项目使用nginx做服务器。

该项目是一个前后端分离博客系统，总共分为三部分，blog-api是spring boot实现的后端应用，使用到了mysql和redis；blog-cms是使用vue实现的后台管理系统的前端，调用blog-api的接口；blog-view是使用vue实现的博客系统前端，调用blog-api的接口实现相关逻辑。

预览地址：
前台：[https://naccl.top](https://naccl.top)
后台：[https://admin.naccl.top](https://admin.naccl.top) 账号`Visitor`密码`123456`

## 使用说明
1. 修改spring boot项目 blog-api的数据库与redis配置信息，在blog-api/src/main/resources/application-dev.properties。
2. 分别到3个项目下执行docker build . 构建 docker image 并上传到镜像仓库。
3. 使用每个项目目录下k8s-app文件部署k8s应用，需要修具体的镜像地址

企业级业务系统的360度立体监控:https://help.aliyun.com/practice_detail/419529?spm=a2c4g.26937898.0.0.75ed5ab2iGHzIU
