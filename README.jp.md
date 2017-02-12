# ChatCenteriO Web/Javascript インストールガイド
## 目次
1. [導入ガイド](#quickstart)
2. [コードのインストール](#install)
3. [カスタマイズ](#customize)

## 導入ガイド<a name="quickstart"></a>

ChatCenter iOのサイトにて、

1. アカウントの作成をします。
2. APP_TOKENと、埋め込むsnippetを取得するために、ChatCenteriO のダッシュボードにログインします.
　
 * 以下のページを開きます。 ダッシュボード -> 導入 -> ウェブサイト
 * 埋め込むチャット画面と連携するチーム名を選択します。
 * 埋め込むsnippetコードを画面からコピーします。

4. コピーしたコードを、あなたのサイトのhtmlに埋め込みます。

## コードのインストール<a name="install"></a>

#### 匿名ユーザとのチャット
一般ページへのインストール
カスタマーの情報は、チャットの開始時にサイト訪問者がChatCenteriOのWidget内で入力します。
    
	<script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='APP_TOKEN' data-org-uid='TEAM_NAME' data-style='popup'>
</script> 

#### 認証されたユーザとのチャット
メンバーエリアなど、サイト内の認証が必要な箇所にインストールする場合
お客様のトラッキングを行い場合や、お客様の名前などをチャットに引き継ぐ場合は以下の方法でインストールします。

##### ERB in Rails (Ruby) のサンプル


       <script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='o1JoQE53yiHwrMpEu9Zm' 
	data-org-uid='chatcenter' data-style='popup' 
	data-user-fullname='<%= current_user.name %>',
	data-user-email='<%= current_user.email %>',
	data-user-createdat='<%= current_user.created_at.to_i %>'></script>
	
##### Django (Python) のサンプル

       <script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='o1JoQE53yiHwrMpEu9Zm' 
	data-org-uid='chatcenter' data-style='popup' 
	data-user-fullname='{{ request.user.name }}',
	data-user-email='{{ request.user.email }}',
	data-user-createdat='{{ request.user.date_joined | date: "U" }}'></script>
	
##### PHP のサンプル

       <script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='o1JoQE53yiHwrMpEu9Zm' 
	data-org-uid='chatcenter' data-style='popup' 
	data-user-fullname='<?php echo $current_user->name ?>',
	data-user-email='<?php echo $current_user->email ?>',
	data-user-createdat='<?php echo strtotime($current_user->created_at) ?>'></script>

##### パラメータ一覧

Parameter name|Description
---|---
data-app-token     | ダッシュボードにより提供されるAPP_TOKENを渡します
data-org-uid       | “My First Team”のTEAM_UIDを渡します
data-style         | チャットの表示の仕方を、“popup”(ポップアップウィンドウ) <br>or “normal”(ページ内にチャット画面を表示する)のどちらかから選びます。
deta-user-fullname | サイト訪問者のフルネーム
data-user-email| サイト訪問者の email.
data-user-createdate| サイト訪問者の情報が作成された日付


## カスタマイズ<a name="customize"></a>

チャット表示のアイコン画像や位置などをカスタマイズしたい場合は、以下のCSSコードをお客様のhtmlページに埋め込むことでカスタマイズすることができます。

#### チャットを開くのアイコン画像の変更

``` 
<style type="text/css">
  #cw-root #cw-button-open-widget {
    background: url("[ICON_IMAGE_URL") !important;
  }
</style>
```

#### アイコン画像のサイズの変更
```
<style type="text/css">
  #cw-root #cw-button-open-widget {
    width: 40px !important;;
    height: 40px !important;;
    background-size:40px !important;
  }
</style>
```

### アイコン画像の位置の変更
```
<style type="text/css">
  #cw-root #cw-button-open-widget {
    position: fixed !important;
    right: 20px !important;
    bottom: 20px !important;
  }
</style>
```

### PCとモバイルで設定を切り替えたい場合は以下の記述の中に上記の設定をお書き込みください
```
<style type="text/css">
  #cw-root #cw-button-open-widget {
    @media (max-width: $screen-md-min) {
      // For mobile & tablet
    }

    @media (min-width: $screen-md-min) {
      // For PC
    }
  }
</style>
```


