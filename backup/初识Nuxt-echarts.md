## Nuxt Echarts

echarts专门为nuxt开发了一个库，需要引用和配置

刚开始使用，就碰到了一个问题：图表如何自适应宽度

解决办法：VChart组件的ref有个resize的方法，每次页面大小变化的时候，应该去触发resize函数

```
//template
<VChart ref="chartRef" :option="option" />

//script
const chartRef = ref(null);
onMounted(() => {
    window.addEventListener('resize', resizeHandler)
})

onUnmounted(() => {
    window.removeEventListener('resize', resizeHandler)
})

function resizeHandler() {
    chartRef.value?.resize()
}
```