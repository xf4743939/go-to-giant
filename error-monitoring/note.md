# 前端错误监控

错误监控文章(https://segmentfault.com/a/1190000021029136)

## 前端错误分类

- 即时运行错误,代码错误
- 资源加载错误,如 js,css 加载失败等

## 错误的捕获方式

- 即时运行错误的捕获
  1. try catch
  2. window onerror
- 资源加载错误的捕获
  1. object.onerror
  2. performance.getEntries()
  3. Error 事件捕获
- 跨域的 javascript 运行错误可以捕获?应该怎么处理?
  1. 在客户端 script 标签添加 crossorigin 属性
  2. 在服务端 javascript 资源响应头设置 Access-control-allow-Origin:\*

## 上报错误的基本原理

1. 采用 Ajax 通信的方式上报(不常用)
2. 采用 Image 对象上报(常用)

## 数据采集

### 性能数据采集

Performance 接口可以获取到当前页面中与性能相关的信息

```js
//link,script,img,css,fetch,other,xmlHttpRequest
window.performance.getEntriesByType("resource");
```
