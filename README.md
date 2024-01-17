# BT-Server-Monitor
一个基于宝塔面板 API 的服务器状态监控面板

演示：https://status.misaliu.top/

## 已经弃坑嘞

因为我自己已经换到哪吒面板来做服务器状态了，所以这个坑就不继续更新了，如果有需求的话可以继续 fork 了再更新也没问题的（记得遵守开源协议！）。

不过你也可以看看我给哪吒面板做的 MDUI 主题：[MisaLiu/nezha-theme-mdui](https://github.com/MisaLiu/nezha-theme-mdui)，跟这个长得基本是一样的。

## 特点

- 使用 PHP 制作，部署简单
- 使用宝塔 API，无需部署其他环境
- 漂亮的自适应 Material Design 样式（来自 [MDUI](https://mdui.org)）

## 安装
1. 登录你服务器的宝塔面板，点击 `设置`；
2. 打开 `API 接口` 开关，记录对应密钥，然后在 `IP 白名单` 中填写 `127.0.0.1`，保存；
3. 下载本仓库源码，打开 `/src/get.php`，将你希望显示的服务器名称、服务器的面板地址 *（带端口号，不带入口地址）* 、服务器的 APIKEY 填写进对应的位置，保存；
4. 上传该 `get.php` 至对应的子服务器，并配置为一个可访问的站点；
5. 打开 `/src/js/main.js`，在文件最上面依次添加每台子服务器的 `get.php` 可被访问的地址进入数组，保存；
6. 上传 `/src` 下的所有文件至主服务器，并配置好网站即可完成~

## 一些问题

### 1、子服务器可能会返回 `404`？
可能是因为访问间隔过短，你可以尝试注释掉 `get.php` 头上的监测访问间隔的代码然后重试。

其他的我想不出来，等有人提 issue 我再更新吧233


## 鸣谢
- [宝塔面板](https://bt.cn)
- [zdhxiong/MDUI](https://github.com/zdhxiong/mdui)
