
* 集成哪吒探针，可以自由选择是否安装
* uuid，WS 路径既可以自定义，又或者使用默认值
* 前端 js 定时和 pm2 配合保活，务求让恢复时间减到最小
* 节点信息以 V2rayN / Clash / 小火箭 链接方式输出
* 项目路径 `https://github.com/fscarmen2/Render`

* PaaS 平台用到的变量
  | 变量名        | 是否必须 | 默认值 | 备注 |
  | ------------ | ------ | ------ | ------ |
  | UUID         | 否 | de04add9-5c68-8bab-950c-08cd5320df18 | 可在线生成 https://www.zxgj.cn/g/uuid |
  | WSPATH       | 否 | argo | 勿以 / 开头，各协议路径为 `/WSPATH-协议`，如 `/argo-vless`,`/argo-vmess`,`/argo-trojan`,`/argo-shadowsocks` |
  | NEZHA_SERVER | 否 |        | 哪吒探针服务端的 IP 或域名 |
  | NEZHA_PORT   | 否 |        | 哪吒探针服务端的端口 |
  | NEZHA_KEY    | 否 |        | 哪吒探针客户端专用 Key |
  | ARGO_TOKEN   | 否 |        | Argo 的 Token，ARGO_TOKEN 与 ARGO_DOMAIN 必需一起填了才能生效 |
  | ARGO_DOMAIN  | 否 |        | Argo 的域名，ARGO_TOKEN 与 ARGO_DOMAIN 必需一起填了才能生效 |

* 需要应用的 js
  | 命令 | 说明 |
  | ---- |------ |
  | <URL>/list | 查看节点数据 |
  | <URL>/status | 查看后台进程 |
  | <URL>/listen | 查看后台监听端口 |


<img width="1011" alt="image" src="https://user-images.githubusercontent.com/92626977/215507678-ec03089e-4612-4cdc-880d-11470f64df0f.png">
<img width="1297" alt="image" src="https://user-images.githubusercontent.com/92626977/215507892-b50d7935-aa8b-4a28-8d35-7e6a3ca62621.png">
<img width="1405" alt="image" src="https://user-images.githubusercontent.com/92626977/215509099-fec65804-f9a9-4fa0-adff-25eee1ed6a75.png">
<img width="1287" alt="image" src="https://user-images.githubusercontent.com/92626977/215508740-c0e8d982-5351-4593-8b37-0f25bbde0eab.png">