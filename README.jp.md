# ChatCenteriO Web/Javascript インストールガイド
## 目次
1. [Quick Start Guide / Installing ChatCenter iO on your Project](#quickstart)
2. [コードのインストール](#install)
3. [Customize](#customize)

## Quick Start Guide / Installing ChatCenter iO on your Project<a name="quickstart"></a>

ChatCenter iOのサイトにて、

1. アカウントの作成をします。
2. APP_TOKENと、埋め込むsnippetを取得するために、ChatCenteriO のダッシュボードにログインします.
　
 * 以下のページを開きます。 ダッシュボード -> 導入 -> ウェブサイト
 * 埋め込むチャット画面と連携するチーム名を選択します。
 * 埋め込むsnippetコードを画面からコピーします。

4. コピーしたコードを、あなたのサイトのhtmlに埋め込みます。

## コードのインストール<a name="install"></a>

#### 匿名ユーザとのチャット
Install for leads visiting logged-out pages
Use on pages where you want to have conversations with logged-out visitors to your site.
    
	<script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='APP_TOKEN' data-org-uid='TEAM_NAME' data-style='popup'>
</script> 

#### Identified Users
Install for users on logged-in pages
Needed on pages where you want to track data  have in-app conversations with logged-in users of your site.

##### Example code for ERB in Rails (Ruby)


       <script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='o1JoQE53yiHwrMpEu9Zm' 
	data-org-uid='chatcenter' data-style='popup' 
	data-user-fullname='<%= current_user.name %>',
	data-user-email='<%= current_user.email %>',
	data-user-createdat='<%= current_user.created_at.to_i %>'></script>
	
##### Example code for Django (Python)

       <script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='o1JoQE53yiHwrMpEu9Zm' 
	data-org-uid='chatcenter' data-style='popup' 
	data-user-fullname='{{ request.user.name }}',
	data-user-email='{{ request.user.email }}',
	data-user-createdat='{{ request.user.date_joined | date: "U" }}'></script>
	
##### Example code for PHP

       <script src='http://widget.chatcenter.io/widget/downloader.js'  id='downloaderjs' data-app-token='o1JoQE53yiHwrMpEu9Zm' 
	data-org-uid='chatcenter' data-style='popup' 
	data-user-fullname='<?php echo $current_user->name ?>',
	data-user-email='<?php echo $current_user->email ?>',
	data-user-createdat='<?php echo strtotime($current_user->created_at) ?>'></script>

#####Parameters

* data-app-token: Replace with Your APP_TOKEN provided in your dashboard.
* data-org-uid: Replace with your ORG_UID of your “My First Team”.
* data-style: Select widget style. “popup”(popup-window chat) or “normal”(Inside-window chat)
* deta-user-fullname: Customer's full name.
* data-user-email: Customer’s email.
* data-user-createdat: 

