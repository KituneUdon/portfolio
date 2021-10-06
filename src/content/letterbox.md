---
layout: post
title: 'Letter Box (システム開発中)'
author: [Yudai Nakajima]
tags: ['Portfolio']
image:
date: '2021-06-06T23:46:37.121Z'
draft: false
excerpt: Profile
---

# 概要

顧客が店舗従業員に対して匿名メッセージを送れるシステム  
目安箱を Web アプリ化したイメージ  
本システムは以下３つのシステムで構成されている

- 顧客メッセージ送信用 Web アプリ
- 店舗従業員メッセージ確認用 Web アプリ
- バックエンド

それぞれのソースコードは以下の通り

顧客メッセージ送信用 Web アプリ  
https://github.com/yudai-nakajima/letter-box-frontend-management

店舗従業員メッセージ確認用 Web アプリ  
https://github.com/yudai-nakajima/letter-box-frontend-client

バックエンド  
https://github.com/yudai-nakajima/letter-box-backend

また、API 仕様書を OpenAPI に基づいて作成している  
https://github.com/yudai-nakajima/letter-box-api

# 作成経緯

Rails チュートリアルを一通りやったので、Rails + React でアプリを作成したかった  
また、各言語それぞれで達成したい目標は以下の通り。

## Rails

- API モードを扱ってみたい
- Rails で認証用 Gem で一番有名であろう devise を触りたい

## React

- ある程度大きい規模のアプリで Atomic Design に則った構成を組みたい

# 機能一覧

フロントエンドは顧客用と店舗従業員用の 2 つに分かれているので、  
それぞれに分けて機能一覧を記述する

## 顧客用

- メッセージ送信機能

### サンプル動画

店舗・従業員を選択してメッセージ送信する一連の流れを動画化している

https://youtu.be/UYMCDHHeB_U

## 店舗従業員用

- ログイン機能
  - 店舗アカウントと従業員アカウント 2 種類のアカウントが存在する
- メッセージ確認機能
- (店舗アカウントのみ) 従業員登録機能

### サンプル動画

#### 従業員ログイン ~ メッセージ確認

従業員アカウントでログイン後、メッセージを確認する画面へ遷移する様子を動画化している。

https://youtu.be/UYMCDHHeB_U

# 使用技術

## React

- react-router-dom
- storybook
- chromatic
- axios
- axios-mock-adapter

## Rails

- devise
- devise-jwt
- rspec

# 反省点

## 認証にトークンを用いたくそのために devise-jwt を採用したがこの選択は失敗だった

devise-jwt は cookie を利用できないための Gem だと Readme に書いてあった

> This gem is just a replacement for cookies when these can't be used

ここを読まずに名前だけで gem を選定した。
今回は cookie を利用できるので他の gem を使用したほうが良かった。

## API 仕様書を open api で作成したが有効活用できなかった

1. API 仕様書作成
2. Rails エンドポイント作成 API
3. 仕様書に沿っているかテストする

上記流れで開発を進めたかったが、  
Rails の理解度が低く 2→1 の順序になってしまった。  
順序が逆になったことで API 仕様書を作成するモチベーションが低下し、  
API 仕様書の管理が雑になった。  
実際、Rails でコードを作成したが API 仕様書に反映していない  
エンドポイントが存在する。

### API 仕様書を作成する当初のモチベ-ション

- committee-rails を用いてテストを実装する
- フロントエンドを先に開発することもできるようにする
  - Prism を用いて API 仕様書に基づいたモックサーバを立てる
