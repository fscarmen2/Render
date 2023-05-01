* 使用 CloudFlare 的 Argo 隧道，同时兼容 Json / token / 临时 三种方式认证，使用TLS加密通信，可以将应用程序流量安全地传输到Cloudflare网络，提高了应用程序的安全性和可靠性。此外，Argo Tunnel也可以防止IP泄露和DDoS攻击等网络威胁
* 解锁 chatGPT
* 在浏览器查看系统各项信息，方便直观
* 集成哪吒探针，可以自由选择是否安装，支持 SSL/TLS 模式，适配 Nezha over Argo 项目: https://github.com/fscarmen2/Argo-Nezha-Service-Container
* uuid，WS 路径既可以自定义，又或者使用默认值
* 前端 js 定时和 pm2 配合保活，务求让恢复时间减到最小
* 节点信息以 V2rayN / Clash / 小火箭 链接方式输出
* 可以使用浏览器访问，使用 ttyd，ssh over http2
* 项目路径 `https://github.com/fscarmen2/Render`

* PaaS 平台用到的变量
  | 变量名        | 是否必须 | 默认值 | 备注 |
  | ------------ | ------ | ------ | ------ |
  | UUID         | 否 | de04add9-5c68-8bab-950c-08cd5320df18 | 可在线生成 https://www.zxgj.cn/g/uuid |
  | WSPATH       | 否 | argo | 勿以 / 开头，各协议路径为 `/WSPATH-协议`，如 `/argo-vless`,`/argo-vmess`,`/argo-trojan`,`/argo-shadowsocks` |
  | NEZHA_SERVER | 否 |        | 哪吒探针与面板服务端数据通信的IP或域名 |
  | NEZHA_PORT   | 否 |        | 哪吒探针服务端的端口 |
  | NEZHA_KEY    | 否 |        | 哪吒探针客户端专用 Key |
  | NEZHA_TLS    | 否 |        | 哪吒探针是否启用 SSL/TLS 加密 ，如不启用不要该变量，如要启用填"1" |
  | ARGO_AUTH    | 否 |        | Argo 的 Token 或者 json 值 |
  | ARGO_DOMAIN  | 否 |        | Argo 的域名，须与 ARGO_DOMAIN 必需一起填了才能生效 |
  | WEB_USERNAME | 否 | admin  | 网页的用户名 |
  | WEB_PASSWORD | 否 | password | 网页的密码 |
  | SSH_DOMAIN   | 否 |        | webssh 的域名，用户名和密码就是 <WEB_USERNAME> 和 <WEB_PASSWORD> |

* 路径（path）
  | 命令 | 说明 |
  | ---- |------ |
  | <URL>/list | 查看节点数据 |
  | <URL>/status | 查看后台进程 |
  | <URL>/listen | 查看后台监听端口 |


<img width="1011" alt="image" src="https://user-images.githubusercontent.com/92626977/215507678-ec03089e-4612-4cdc-880d-11470f64df0f.png">
<img width="1297" alt="image" src="https://user-images.githubusercontent.com/92626977/215507892-b50d7935-aa8b-4a28-8d35-7e6a3ca62621.png">
<img width="1405" alt="image" src="https://user-images.githubusercontent.com/92626977/215509099-fec65804-f9a9-4fa0-adff-25eee1ed6a75.png">
<img width="1287" alt="image" src="https://user-images.githubusercontent.com/92626977/215508740-c0e8d982-5351-4593-8b37-0f25bbde0eab.png">

* 原理
```
+---------+     argo     +---------+     http     +--------+    ssh    +-----------+
| browser | <==========> | CF edge | <==========> |  ttyd  | <=======> | ssh server|
+---------+     argo     +---------+   websocket  +--------+    ssh    +-----------+
```

* ttyd 只能使用 Json 方式建的隧道，不能使用 Token
  
<img width="1643" alt="image" src="https://user-images.githubusercontent.com/92626977/235453084-a8c55417-18b4-4a47-9eef-ee3053564bff.png">
<img width="1347" alt="image" src="https://user-images.githubusercontent.com/92626977/235453394-2d8fd1e9-02d0-4fa6-8c20-dda903fd06ae.png">
<img width="983" alt="image" src="https://user-images.githubusercontent.com/92626977/235453962-1001bcb8-e21d-4c1b-9b8f-6161706f5ccd.png">
<img width="1540" alt="image" src="https://user-images.githubusercontent.com/92626977/235454653-3ac83b16-b6f4-477b-bccf-2cce8bcfbabe.png">