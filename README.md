code-gen
一款代码生成工具，可自定义模板生成不同的代码，支持MySQL、Oracle、SQL Server、PostgreSQL。

只需要一个Java8环境，下载后即可运行使用。
步骤简单，只需配置一个数据源，然后勾选模板即可生成代码。
默认提供了通用的实体类、mybatis接口、mybatis配置文件模板，可以快速开发mybatis应用。
用到的技术：SpringBoot + Mybatis + Vue

使用步骤
前往发行版页面，下载最新版本zip文件
解压zip，如果是Mac/Linux操作系统，运行startup.sh文件启动，Windows操作系统运行cmd输入java -jar gen.jar启动
浏览器访问http://localhost:6969/
默认端口是6969，更改端口号按如下方式：

Mac/Linux操作系统：打开startup.sh文件，修改--server.port参数值
Windows操作系统：可执行：java -jar gen.jar --server.port=端口号
docker运行
方式一：下载公共镜像
docker pull tanghc2020/gen:latest

下载完毕后，执行docker run --name gen -p 6969:6969 -d <镜像ID>

浏览器访问http://ip:6969/

方式二：本地构建镜像
clone代码，然后执行docker-build.sh脚本

执行docker run --name gen -p 6969:6969 -d <镜像ID>

其它
快速搭建SpringBoot+Mybatis应用
更多模板
代码生成器原理
工程说明
front：前端vue
gen：后端服务
db：数据库初始化文件
script：辅助脚本
自主构建
需要安装Maven3，Java8

自动构建[推荐]：
Mac/Linux系统可直接执行build.sh进行构建，构建结果在dist文件夹下。

手动构建：

cd front

执行npm run build:prod进行打包，结果在dist下
把dist中的所有文件，放到gen/src/main/resources/public下
cd ..

执行mvn clean package，在gen/target下会生成一个gen-xx-SNAPSHOT.jar（xx表示本号）
将gen-xx-SNAPSHOT.jar和db下的gen.db放在同一个文件夹下
执行java -jar gen-xx-SNAPSHOT.jar
浏览器访问http://localhost:6969/
效果图
代码生成

生成结果
