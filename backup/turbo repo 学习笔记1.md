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
至此，就可以在应用文件中使用本地自己创建的package