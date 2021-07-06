---
layout: post
title: 'Todo-Storage'
author: [Yudai Nakajima]
tags: ['Portfolio']
image: img/todo-storage-image.png
date: '2021-06-06T23:46:37.121Z'
draft: false
excerpt: Profile
---

# 概要

ログイン機能とタスクの CRUD 操作ができる最低限の機能を搭載した Todo アプリ。

[アプリ](https://todo-strage.web.app)  
アプリには以下ユーザでログイン可能
メールアドレス：example@example.com
パスワード：example

[ソースコード](https://github.com/yudai-nakajima/todo-storage)

# 作成経緯

React の基本を一通り理解したので、それらをアウトプットするためにアプリを作成しようと思いました。
Todo アプリであれば難しくて作成が止まるということがないと思い、Todo アプリにしました。

React に集中したかったためバックエンドは Firebase を使用しました。

# 機能一覧

- ユーザ登録
- ログイン
- タスク管理機能
  - タスクの追加
  - タスクの削除
  - タスクの完了
  - タスクの変更

# 使用技術

- React 17.0.2
- TypeScript 4.1.5
- Firebase
- Firestore
- Firebase Authorization
- ESLint
- Prettier
- Day.js
- Material Ui
- React Router DOM
