## 使用switchMap来简化嵌套订阅

```js
this.userService.getUser().pipe(
  switchMap(user => this.orderService.getOrders(user.id))
).subscribe(orders => {
  console.log(orders);
});
```