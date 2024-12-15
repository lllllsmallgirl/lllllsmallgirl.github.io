## vue3

### 前言：
使用了nuxt框架后，觉得应该学习一下基本vue3的项目，可以接一些简单的vue3项目


### 创建项目

```
$ pnpm create vue@latest
```
项目目录结构如下：
![image](https://github.com/user-attachments/assets/5f18080b-2aca-4ea8-91fd-5ff178bb7475)


### 文件结构增补：
在src下，新建了一个layouts文件夹，用来存放基本布局的文件，用于放在App.vue根组件中


### 添加tailwindcss
参考：https://tailwindcss.com/docs/guides/vite#vue
在assets的main.css里引入tailwindcss，并且可以在这个文件中修改全局的样式
```css
@layer base {
  h1{
    @apply text-[36px] font-[600] m-0;
  }
}
```

### ts无法引入vue组件
遇到了问题：无法找到模块“./layout/MainLayout.vue”的声明文件
原因：ts不认识vue组件
解决办法：
在src下新建shims-vue.d.ts，添加如下代码：
```ts
declare module "*.vue" {
  import { DefineComponent } from "vue";
  const component: DefineComponent<{}, {}, any>;
  export default component;
}

```


### 引入iconify
参考：https://iconify.design/docs/usage/css/tailwind/
需要在开发环境引入以下两个库，都要安装，第一个在文档中没写
```js
    "@iconify-json/uil": "^1.2.1",
    "@iconify/tailwind": "^1.2.0",
```
第一个库需要什么就安装什么，看后缀，不然全部安装的话感觉会很大，有120mb


### 引入shadcn-vue
参考：https://www.shadcn-vue.com/docs/installation/vite.html


### 路由
useRouter和useRoute
useRouter用于导航操作，比如跳转等
useRoute用于获取当前路由状态，用于获取params，query等

监听路由变化：利用watch
```
   // 监听路由变化
    watch(
      () => route.path, // 监听 path 属性
      (newPath, oldPath) => {
        console.log(`路由从 ${oldPath} 变为 ${newPath}`);
        routePath.value = newPath; // 更新路径
      }
    );

    // 监听路由的 params 变化
    watch(
      () => route.params,
      (newParams, oldParams) => {
        console.log('路由参数变化：', newParams, oldParams);
      },
      { deep: true } // 深度监听，确保子属性变化也被捕获
    );

    // 监听路由的 query 变化
    watch(
      () => route.query,
      (newQuery, oldQuery) => {
        console.log('路由查询参数变化：', newQuery, oldQuery);
      }
    );

```



