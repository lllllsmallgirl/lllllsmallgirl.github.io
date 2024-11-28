## 问题描述
1. 点击侧边菜单栏，
     1）可以弹出选项卡，
     2）并且选项卡activity，路由跳转
2. 点击tab选项卡，可以路由跳转
3. tab选项卡删除的问题

## 所需知识
vue router、watch
const route = useRoute()
const router = useRouter()
router.push('/xxx') 路由跳转到/xxx
watch(
    () => route.path, // 仅监听路径变化
    (newPath, oldPath) => {
    },
    { immediate: true }
);

## 解决办法
1. 由于已经实现了菜单栏点击路由跳转，所以想到通过监听路由的变化来查找当前的tabs数据中是否存在属性为该路由的元素，如果存在，则设置tab的activity，如此可解决2）
如果不存在，就构建一个子元素，并push进tabs数据，解决1）
2. 点击tab加载不同的组件，其实就是路由跳转，只要在tab的数据中加上对应的path，接着绑定点击事件即可解决
3. 实现remove方法，并需要考虑如下问题：
  a. 如果删除的不是active，且不是首尾元素，则属于正常情况
  b. 如果删除的是active，则把active设置为前一个元素
  c. 如果删除的是首/尾元素，则active设置为下一个/上一个元素










