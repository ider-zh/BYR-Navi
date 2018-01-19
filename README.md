# LMD NAV
> 本项目源自[BYR-NAVI](https://github.com/BYR-Navi/BYR-Navi)

本项目使用 Ruby 工具 [Jekyll](http://jekyll.com.cn/) 构建的静态导航站点,项目侧重点在部署上.

主要步骤

+ Ruby 环境搭建
+ 搭建支持服务 Piwiki
+ 站点修改
+ 容器部署


## Ruby 环境搭建

Ubuntu 自带 ruby, 但是安装 Gem 包会有权限和依赖问题,这个不好解决.所以本次使用 Ruby 环境管理工具 [RVM](https://ruby-china.org/wiki/rvm-guide),管理 Ruby 版本和 Gem 包.

使用 RVM 安装完成 Ruby 和创建 Gem 空间后, 还需要更换一下 gem 源加速, 使用 [Ruby China](https://gems.ruby-china.org/)
在项目目录下使用 `gem install -g` 完成依赖安装

使用 `jekyll server` 启动服务, 预览当前站点
jekyll 在项目根目录下生成一个 _site 文件夹,包含静态站点的所有文件

## 搭建支持服务 piwiki

piwiki 是一个开源的流量统计服务, 使用 PHP 开发. 将过程包装成 [Docker镜像](https://hub.docker.com/r/ider/piwiki/),在该项目组中使用

## 站点修改

主要是清理修改站点上的一些内容, 使用自己的统计 key

## 容器部署

最后一个环节, 将站点包装到 Docker 镜像中, 使用当前目录下的 Dockerfile 完成构建

一键运行
`docker run --rm  -p 8080:80 -it ider/lmdnav
