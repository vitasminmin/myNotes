## 在网页中会引用那些常见的静态资源

+ JS
  + .js  .jax  .coffee  .ts 

- CSS
  + css	less	sass	scss

- Images
  + jpg	png	gif	

- 字体文件
  - svg 	ttf 	eot	woff	woff2
- 模版文件
  + ejs	jade	vue



## 网页中引入了过多的静态资源以后有什么问题

1. 网页加载速度慢，因为发起的二次请求多。
2. 要处理错中复杂的依赖关系。
3. 要解决需要合并、压缩、精灵图（雪碧图）、图片的base64编码（适用小图）。



## 什么是webpack

是前端的项目构建工具 ，基于nodejs开发，依赖nodejs环境运行。



## 如何完美解决上述问题

1. 使用Gulp。

   基于task任务的，小巧灵活，应对大型项目有些繁琐。

2. 使用Webpack

   + 借用webpack这个前段模块自动化构建工具，可以完美实现资源的合并、打包、压缩、混淆等诸多功能。
   + 

## webpack能做什么

- 可以处理JS文件的依赖关系；
- 可以处理JS的兼容问题，把高级的、浏览器不识别的方法转为低级别的浏览器可以识别的语法。 

- 当在控制台输入webpack命令时，如果没有指定入口和出口，webpack就会去项目根目录寻找webpack.config.js。
- 当找到配置文件后，解析之行文件，解析后找到导出的配置对象
- 找到配置对象后，就找到了入口和出口，然后进行打包。



## webpack-dev-server工具，实现自动打包编译

- npm i webpack-dev-server -D 安装到开发依赖
- 可以直接使用命令行webpack-dev-server进行启动，也可以写到package.json，scripts脚步中，使用命令npm run dev进行执行
- 启动后会新开8080服务，
  + 这个端口可以使用--port 2000进行设置，
  + --open可以设置启动自动打开浏览器,
  + --contentBase src 可以设置跟路径。
  + --hot 补丁式更新，不必完全重新生成bundle.js，可以实现浏览器无刷新重载
  + 完整设置  webpack-dev-server --open --port 3000 --contentBase src --hot
- 注意此时工具帮我们打包生成的bundle.js，是在项目根目录下。同时该文件是虚拟的并没有存放到硬盘上（看不到），这样做的目的是快同时减少磁盘读写。



## html-webpack-plugin插件实现html内存首页

- 安装命令 npm i html-webpack-plugin -D，-D是--save-dev的简写，-S是--save的简写，-g是全局安装--global的简写。
- 自动在内存中根据指定首页生成内存首页。
- 使用该插件后，会自动在html中插入bundle.js的引用。



## css loader使用

- webpack默认只能打包处理 JS 类型的文件，无法处理CSS类型文件
- 若要处理非JS类型文件，需要安装一些合适的第三方loader加载器
- 打包处理CSS类型文件，需要安装npm i style-loader css-loader -D
- 打开webpack.config.js配置文件，在里面新增一个配置节点，叫module，是一个对象；在这个module对象上，有个数组对象rules，存放所有的第三方文件的匹配和处理规则。



## webpack处理第三方文件的过程

1. 发现要处理的不是JS文件，然后就会去配置文件查找有没有对应的第三方 loader 规则
2. 如果找到规则，就会调用对用的loader处理这种文件类型
3. 调用loader顺序是从后往前调用
4. 当最后的一个loader调用完毕，将结果传给webpack合并到bundle.js