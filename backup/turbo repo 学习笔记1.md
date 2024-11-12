monorepo概念：单仓 同时管理多个项目
turbo repo：采用monorepo的项目管理框架

## 安装
1. 全局安装turbo：npm install turbo --global
2. 创建一个turborepo项目：npx create-turbo@latest

## 创建内部package
在packages文件夹下，新建文件夹，然后创建package.json
```
"exports":{
    "./add": "./src/add.ts
}
```
创建出口，就是对外暴露的方法

在应用文件夹中的package.json中添加本地依赖，添加后一定记得pnpm i，把本地的包引入！！！
在根目录下执行pnpm i即可，内部的都会自动链接上
至此，就可以在应用文件中使用本地自己创建的package

## 创建nuxt项目
1. 在apps文件夹下，打开终端
2. 执行 npx nuxi@latest init <project-name>  初始化一个新的nuxt.js项目
3. 在nuxt的package.json中，添加共享package的依赖
```
在应用文件夹中的package.json中添加本地依赖，添加后一定记得pnpm i，把本地的包引入！！！
在根目录下执行pnpm i即可，内部的都会自动链接上
至此，就可以在应用文件中使用本地自己创建的package
```
4. 现在就可以在nuxt项目中使用共享包的内容了，以后可以把公共组件全放在一个叫ui的共享package中


## TODO
学习tsconfig文件，之前新建共享包的时候，也应该添加tsconfig文件，暂时还没添加