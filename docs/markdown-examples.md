# vitepress上传github

过程记录

## 

**报错记录 npm run docs:preview**

````md

PS D:\zyy-code-house\vitepress\vt> npm run docs:preview

> docs:preview
> vitepress preview docs --port 8080


  vitepress v1.5.0

node:events:497
      throw er; // Unhandled 'error' event
      ^

Error: listen EADDRINUSE: address already in use :::8080
    at Server.setupListenHandle [as _listen2] (node:net:1904:16)
    at listenInCluster (node:net:1961:12)
    at Server.listen (node:net:2063:7)
    at Polka.listen (file:///D:/zyy-code-house/vitepress/vt/node_modules/vitepress/dist/node/chunk-DMuPggCS.js:52182:22)       
    at serve (file:///D:/zyy-code-house/vitepress/vt/node_modules/vitepress/dist/node/chunk-DMuPggCS.js:52896:55)
Emitted 'error' event on Server instance at:
    at emitErrorNT (node:net:1940:8)
    at process.processTicksAndRejections (node:internal/process/task_queues:82:21) {
  code: 'EADDRINUSE',
  errno: -4091,
  syscall: 'listen',
  address: '::',
  port: 8080
}

Node.js v20.18.0

````

**解决方案**
````
Windows:
使用命令提示符或 PowerShell 执行以下命令来查找占用端口的进程 ID (PID)：
netstat -ano | findstr :8080
然后使用任务管理器结束该 PID 的进程，或者直接在命令行中执行：
taskkill /PID <PID> /F
````
## Custom Containers

**Input**

```md
::: info
This is an info box.
:::

::: tip
This is a tip.
:::

::: warning
This is a warning.
:::

::: danger
This is a dangerous warning.
:::

::: details
This is a details block.
:::
```

**Output**

::: info
This is an info box.
:::

::: tip
This is a tip.
:::

::: warning
This is a warning.
:::

::: danger
This is a dangerous warning.
:::

::: details
This is a details block.
:::

## More

Check out the documentation for the [full list of markdown extensions](https://vitepress.dev/guide/markdown).
