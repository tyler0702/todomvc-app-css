graph TB
  subgraph Client ["クライアント"]
    UI["ユーザーインターフェース"]
    ClientLogic["クライアントサイドロジック"]
  end

  subgraph Server ["サーバ"]
    APIServer["APIサーバ"]
    MessageService["メッセージ処理サービス"]
    NotificationService["通知サービス"]
  end
  
  subgraph Database ["データベース"]
    MessageDB["メッセージDB"]
    UserDB["ユーザーDB"]
  end
  
  subgraph Infrastructure ["インフラストラクチャ"]
    LoadBalancer["ロードバランサー"]
    Cache["キャッシュ"]
  end
  
  subgraph Security ["セキュリティと認証"]
    AuthServer["認証サーバ"]
    Encryption["エンドツーエンド暗号化"]
  end
  
  subgraph Monitoring ["監視とロギング"]
    LogServer["ログサーバ"]
    MonitoringTools["監視ツール"]
  end
  
  subgraph ThirdParty ["サードパーティサービス"]
    PushNotification["プッシュ通知サービス"]
    EmailService["メールサービス"]
  end

  UI -->|リクエスト送信| ClientLogic
  ClientLogic -->|APIリクエスト| APIServer
  APIServer -->|メッセージ配信| MessageService
  APIServer -->|通知送信| NotificationService
  MessageService -->|メッセージ保存| MessageDB
  MessageService -->|ユーザー情報取得| UserDB
  NotificationService -->|プッシュ通知| PushNotification
  NotificationService -->|メール通知| EmailService
  LoadBalancer -->|トラフィック分散| APIServer
  APIServer -->|データキャッシュ| Cache
  APIServer -->|ユーザー認証| AuthServer
  ClientLogic -->|メッセージ暗号化| Encryption
  APIServer -->|ログ記録| LogServer
  APIServer -->|システム監視| MonitoringTools




# todomvc-app-css

> CSS for TodoMVC apps

![](screenshot.png)


## Install


```
$ npm install --save todomvc-app-css
```


## Getting started

```html
<link rel="stylesheet" href="node_modules/todomvc-app-css/index.css">
```

See the [TodoMVC app template](https://github.com/tastejs/todomvc-app-template).



## License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/deed.en_US"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/4.0/80x15.png" /></a><br />This <span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/InteractiveResource" rel="dct:type">work</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="http://sindresorhus.com" property="cc:attributionName" rel="cc:attributionURL">Sindre Sorhus</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/deed.en_US">Creative Commons Attribution 4.0 International License</a>.
