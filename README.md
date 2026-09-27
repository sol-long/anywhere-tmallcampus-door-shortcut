# anywhere-tmallcampus-door-shortcut

一键直达天猫校园 App「点我开门」界面的桌面快捷方式，免去「打开 App → 找入口 → 点我开门」的重复操作。

## 原理

- 天猫校园支持 `tmallcampus://` DeepLink scheme
- `tmallcampus://web/open?url=<URL编码>` 可让 App 打开任意 H5 页面
- 「点我开门」本质是 H5 页面，通过 WindVane JSBridge（`vocLock` / `ZMUnlockJsBridge`）控制蓝牙门锁，非独立 native 页面
- 跳转链路：`tmallcampus://` → DispatchActivity → Navigator → `/web/open` → 解码 url → doorLock 页

## Deep Link

```
tmallcampus://web/open?url=https%3A%2F%2Fbiz.confong.cn%2Fapp%2Ftmall-xiaoyuan%2Fpage-m-webview%2FdoorLock%3FloginRequired%3Dtrue%26hideNavigator%3Dtrue
```

对应 H5 页面：`https://biz.confong.cn/app/tmall-xiaoyuan/page-m-webview/doorLock?loginRequired=true&hideNavigator=true`

## 使用方式

### Android

用「Web Shortcut / ADB Shortcut」类 App 创建快捷方式，URL 填 deep link；或浏览器打开后「添加到主屏幕」。

### iPhone

快捷指令 App → 新建「打开 URL」→ 填入 deep link → 添加到主屏幕

## [anywhere-分享链接](anywhere-.md)

## 免责声明

仅供学习研究，与天猫/淘宝官方无关；功能可能随 App 版本变化。
