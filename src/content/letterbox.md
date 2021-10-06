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

店舗利用者が店舗従業員に対して匿名メッセージを送れるシステム  
本システムは以下３つのシステムで構成されている

- 店舗利用者メッセージ送信フロントエンド
- 店舗従業員メッセージ確認フロントエンド
- バックエンド

それぞれのソースコードは以下の通り

店舗利用者メッセージ送信フロントエンド  
https://github.com/yudai-nakajima/letter-box-frontend-management

店舗従業員メッセージ確認フロントエンド  
https://github.com/yudai-nakajima/letter-box-frontend-client

バックエンド  
https://github.com/yudai-nakajima/letter-box-backend

また、API 仕様書を OpenAPI に基づいて作成している  
https://github.com/yudai-nakajima/letter-box-api

# 作成経緯

Rails チュートリアルを一通りやったので、Rails + React でアプリを作成したかった  
また、各言語それぞれの作成目的は以下の通り

## Rails

- API モードを扱ってみたい
- Rails で認証用 Gem で一番有名であろう devise を触りたい

## React

- ある程度大きい規模のアプリで Atomic Design に則った構成を組みたい

# 機能一覧

フロントエンドは店舗利用者用と店舗従業員用の 2 つに分けているので、  
それぞれで機能一覧を記述する

## 店舗利用者用

- メッセージ送信機能

### サンプル動画

https://youtu.be/UYMCDHHeB_U

## 店舗従業員用

- ログイン機能
  - 店舗アカウントと従業員アカウント 2 種類のアカウントが存在する
- メッセージ送信機能

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

ここを読まずに名前だけで使用を決定したが、この選択は開発を進めるにつれ失敗だと分かった。  
cookie を利用できるので cookie にトークンを格納する Gem を探して、  
そちらを採用したほうがセキュリティ的にも開発工数的にも良かった。

## API 仕様書を open api で作成したが有効活用できなかった

API 仕様書作成 →Rails エンドポイント作成して API 仕様書に沿っているかテストするという流れで開発を進めたかったが、  
Rails の理解度が低く Rails エンドポイント作成 → API 仕様書作成の順序になってしまった。  
順序が逆になったことで API 仕様書を作成するモチベーションが低下し、API 仕様書の管理が雑になった。
実際、Rails でコードを作成したが API 仕様書に反映していないエンドポイントが存在する。

### API 仕様書を作成する当初のモチベ-ション

- committee-rails を用いてテストを実装する
- フロントエンドを先に開発することもできるようにする
  - Prism を用いて API 仕様書に基づいたモックサーバを立てる
