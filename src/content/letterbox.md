---
layout: post
title: 'Letter Box'
author: [Yudai Nakajima]
tags: ['Portfolio']
image:
date: '2021-06-06T23:46:37.121Z'
draft: true
excerpt: Profile
---

# 概要

店舗利用者が店舗従業員に対して匿名メッセージを送れるシステム
本システムは以下３つのシステムで構成されている

- 店舗利用者メッセージ送信フロントエンド
- 店舗従業員メッセージ確認フロントエンド
- バックエンド

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

- 認証にトークンを用いたくそのために devise-jwt を採用したがこの選択は失敗だった
  - devise-jwt は cookie を利用しない
    - devise-jwt は cookie を使えない環境での選択肢として作成された Gem のため
