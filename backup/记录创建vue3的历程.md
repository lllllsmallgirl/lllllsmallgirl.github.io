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









