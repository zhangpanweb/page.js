**几个要素**

- 注册跳转及回调：page方法 -> this.callbacks.push(route.middleware(arguments[i])) 将路由中间件推入到 callbacks 中 -> start 启动路由 -> dispatch -> 依次执行 callbacks 中的回调，进行路由匹配执行 redirect 及回调等

- 拦截点击事件： configure 方法 _window.document.addEventListener(clickEvent, this.clickHandler, false) 监听全局所有点击事件 -> clickHandler 中最终调用 page.show -> dispatch -> 兜底 pushState

- 监听浏览器回退等：configure 方法 _window.addEventListener('popstate', this._onpopstate, false) 监听 popstate 事件 -> 调用 page.replace 或 page.show 等
