# 项目结构介绍
0. 仿大众点评的前后端分离的项目，前端使用了react-redux框架的SPA（单页面），后端使用了Java SSM,数据库使用MySQL。
1. comment是后台管理系统程序，因为是maven项目，
	eclipse 和 idea以及其他IDE 均可导入。
2. react-dianping是前端项目初始代码，已经删除了node_modules，
	需要安装node.js环境后重新执行npm install，具体步骤见视频。
	该目录下webpack.config.js文件中 "target: 'http://127.0.0.1:8081/comment',"是指向后台，
	如果想要前端app连接mock server ，注释该句，放出上面的“target: 'http://localhost:3000',”
	修改时注意输入法是英文输入法（切忌中文）
3. SQL脚本请先运行createTable.sql建表，再运行loadInitData.sql插入数据
4. 前后端分离了，在于前端有自己的服务器，页面在自己的服务器（不是mock，mock相当于模拟的后端服务器）中，只需要与后台传输json数据；
但是后台管理的页面还是在后台服务器中。

# 如何运行
## 前端工程初始化步骤
1. 安装nodejs环境,推荐使用v4.4.7
    下载地址 : https://nodejs.org/download/release/v4.4.7/

2. 全局安装webpack v^1.15.0
    命令: (sudo) npm install -g webpack@^1.15.0

3. 全局安装webpack-dev-server v^1.16.5
    命令: (sudo) npm install -g webpack-dev-server@^1.16.5


4. 在项目根目录执行npm初始化
    命令: npm install

5. 启动项目
    开发模式: npm run start
    生产模式: npm run build
    mock: npm run mock
    * 不使用mock数据时在哪里修改？ * 
    -- 在webpack.config.js中，devServer的属性改为target: 'http://localhost:8081/comment',

6. 开发模式下预览项目
    访问：http://localhost:3000/dist/view/index.html

## 后端工程初始化步骤
1. 