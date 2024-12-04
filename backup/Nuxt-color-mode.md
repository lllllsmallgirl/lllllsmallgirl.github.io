## Nuxt-Color-Mode
这是nuxt的一个亮暗主题切换的库

### 使用方法：
参考：https://color-mode.nuxtjs.org/

个人配置如下：
1. 其中在nuxt.config.ts中配置的 classSuffix: '' , 这是使用class的类名后缀
比如后缀为空就是：dark: bg-slate-900； 后缀为 '-mode' 就是：dark-mode: bg-slate-900
2. 在tailwindcss.config.js里，添加  darkMode: 'class',

使用：
1. 在class中，class="dark:bg-slate-900 transition-colors duration-300 ease-in"
2. 在style中，
.dark .el-menu-item:hover {
    background-color: #2e3033 !important;
}
