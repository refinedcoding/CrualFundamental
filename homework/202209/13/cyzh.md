## 2022/09/13

### HTTP301和302的区别

#### 301

永久移动。请求的资源已被永久的移动到新URI，返回信息会包括新的URI，浏览器会自动定向到新URI。今后任何新的请求都应使用新的URI代替

#### 302

临时移动。与301类似。但资源只是临时被移动。客户端应继续使用原有URI