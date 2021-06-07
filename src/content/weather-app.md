---
layout: post
title: 'Weather App'
author: [Yudai Nakajima]
tags: ['Portfolio']
image: img/callum-shaw-555357-unsplash.jpg
date: '2021-06-06T23:46:37.121Z'
draft: false
excerpt: Profile
---

# 概要
現在地を取得し、その地点の天気を表示するだけのシンプルな天気アプリです。

[アプリ](https://kituneudon.github.io/weather-app/)
[ソースコード](https://github.com/KituneUdon/weather-app)  
[Storybook](https://www.chromatic.com/builds?appId=60ac4c700647b700446c2f77)

## アプリの動作環境
- chrome
- firefox

# 作成経緯
以下2つの技術を用いてアプリを作成したいと思いました。
- Atomic Design
- Storybook

これらの技術は今まで触れたことがないため、作成難易度が低いアプリのほうが挫折しにくいと考えました。  
また、コンポーネント数を簡単に増やすことができればAtomic Designによるコンポーネントの分割の恩恵を実感しやすいと考えました。  

「現在地を取得し、その地点の天気を表示する」だけのシンプルなアプリであれば難易度は低く、  
表示する情報を増やせば、自然とコンポーネントも増えるため、今回作成するのにぴったりなアプリだと考え、天気アプリを作成しました。  

# 使用技術
- React 17.0.2
- TypeScript 4.1.5
- ESLint
- Prettier
- Storybook
- chromatic + github actionsを用いたテスト
- React Query
- Formik
- Recharts

## 使用API
- Open Weather Map
- Geolocation API
- HeartRails Geo API

# 機能一覧
- 現在地の取得
- 取得した現在地をもとに天気を表示する
- 都市名を検索し、その都市の天気を表示する

# テスト
- Chromaticを用いたスナップショットテスト

# 使用イラストについて
## 天気予報のイラスト
本アプリで使用している天気に関するイラストはすべてイラストや様のものを使用しております。  
https://www.irasutoya.com

使用点数：11点

イラストや様の利用規約  
https://www.irasutoya.com/p/terms.html

## アイコン
### 削除ボタン
Icon rainbowより  
https://icon-rainbow.com/%E7%A6%81%E6%AD%A2%E3%80%81%E9%96%89%E3%81%98%E3%82%8B%E3%81%AE%E3%82%A2%E3%82%A4%E3%82%B3%E3%83%B3%E7%B4%A0%E6%9D%90-2/