 

### 模块加载规则

- 优先从缓存加载

- 判断模块标识

  - 核心模块

    非路径形式的，require名称即可

  - 用户自己写的，require 相对或绝对路径

  - 第三方模块

    + 所有第三方模块必须要使用npm下载
    + 使用的时候就可以通过require包名的方式来进行加载才可以使用
    + 不可能有任何一个第三方的包和核心模块的名字一样 
    + 寻找过程
      1. 先找node_modules目录
      2. 再找该目录下对应的模块名称目录
      3. 再找模块目录下的package json
      4. 找package json中的main属性
      5. 找到main属性对应的js文件，即为模块入口文件  
      6. 如果没有package json或package json没有配置main或main指向的不存在，默认会找index.js

    + 如果条件不成立找不到，则往node_modules上层目录查找，直到磁盘根目录
    + 一般一个项目有且只有一个node_modules，放在项目根目录

  - 自定义模块



## 包文件说明

###  npm

- npm网站

  网站是第三方依赖包的中心，就像maven中央仓库一样

- npm命令行工具

  只要安装了node就安装了npm，npm也有版本的概念，可以使用`npm --version`进行查看

  升级npm

  ```npm install --global npm``

- npm常用命令

  1. npm init ：初始化
  2. npm install ：按照依赖项安装所有包
  3. npm install package-name：按照包名进行下载
  4. Npm install --save：下载时添加到本地依赖，简写是 -S
  5. npm uninstall package-name：卸载依赖
  6. npm uninstall package-name --save：卸载的同时删除本地依赖

- 解决被墙的问题
  淘宝的cnpm镜像安装，每隔10分钟从海外同步一次

  ```npm install --global cnpm```

  安装完cnpm后即可使用`cnpm`命令安装包，同时`npm`还可以使用

  如果不想安装cnpm还想使用淘宝镜像可依使用

  ```javascript
  npm install jquery --registry=https://registry.npm.taobao.org
  ```

  但是每次手动写很麻烦，可以把地址写到配置文件中

  ```javas
  npm config set --registry=https://registry.npm.taobao.org
  # 查看配置信息
  npm config list
  ```

   

### package.json

工程描述，第三方依赖描述

该文件可以通过`npm init`方式初始化出来，根据提示输入信息即可完成

- 建议每个项目跟目录都有该文件
- 建议执行npm install的时候都加上--save选项，npm i 是npm install的简写
- package.json可以在node-modules删除的时候，使用`npm install`命令恢复回来



架构章节：本次变更不涉及

1.3.1

4.1

4.4.15 

修改说明