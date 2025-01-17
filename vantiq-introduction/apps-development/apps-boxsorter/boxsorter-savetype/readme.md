# 荷物仕分けアプリケーション (SaveToType)

荷物仕分けアプリケーション (Standard) を利用して、 Type にデータを保存する方法について学習します。

## 荷物仕分けアプリケーション (SaveToType) の学習概要

開発した荷物仕分けアプリケーションを通じて、追加の Activity Pattern について学びます。  

今回のセッションでは、 `sorting_condition` Type に登録されていない荷物コードがブローカーから送られてきます。  
荷物コードが登録されていない荷物を管理するために、新たに Type を作成し、最新のデータを保存します。

今回のセッションでは、これらの追加改修を行っていきます。  

> **注意**  
> 荷物仕分けアプリケーション (Standard) を実施していない場合は、先に 荷物仕分けアプリケーション (Standard) を実施してください。  
> - [荷物仕分けアプリケーション (Standard)](./../boxsorter-standard/readme.md)

### 学習目的

このワークショップの目的は下記のとおりです。

#### 主目的

1. ActivityPattern の **SaveToType** の使い方を理解する。

## Vantiqで実装する荷物仕分け (Box Sorter) アプリケーション 概要

![vantiq-app.png](./imgs/vantiq-app.png)

このアプリケーションを実装していきます。  
詳細は次のステップで説明しますが、 `AttachCondition` タスクから分岐した処理の実装を行います。

## 荷物仕分けアプリケーションで利用する Activity Pattern の紹介

このワークショップでは下記の Activity Pattern を利用します。
> 荷物仕分けアプリケーション (Beginner) や 荷物仕分けアプリケーション (Standard) で紹介したものは割愛します。  
>
> 詳細は下記を参照してください。  
> - [荷物仕分けアプリケーション (Beginner)](./../boxsorter-beginner/readme.md)
> - [荷物仕分けアプリケーション (Standard)](./../boxsorter-standard/readme.md)

### SaveToType Activity

![activitypattern_savetotype.png](./imgs/activitypattern_savetotype.png)

イベントを Type に保存します。  
保存方法は `INSERT` もしくは `UPSERT` になります。  
`UPSERT` を利用する場合は、 Type の設定で `Natural Key` を事前に設定しておく必要があります。  

## 必要なマテリアル

### 各自で準備する Vantiq 以外の要素

以下のものを事前にご用意ください。

- MQTTブローカー
  - Vantiq から仕分け結果を送信する先として使用します。
  - お好きなブローカーをご利用ください。  
    AmazonMQ などマネージドなものを使っても、 ActiveMQ や Mosquitto をご自身でインストールして準備しても構いません。
  - :globe_with_meridians:[The Free Public MQTT Broker by HiveMQ](https://www.hivemq.com/public-mqtt-broker/) のように無料で使用できるブローカーもございます。
  - Vantiq やご自身のクライアントからアクセスできる必要がありますのでインターネット接続できる必要があります。

以下のいずれかを事前にご用意ください。

- Google Colab
  - Google アカウント（※Google Colaboratory を利用するために使用します）
  - [BoxSorterDataGenerator (SaveToType)](/vantiq-google-colab/docs/jp/box-sorter_data-generator_savetype.ipynb)
- Python
  - Python 実行環境
  - [BoxSorterDataGenerator (SaveToType)](/vantiq-google-colab/docs/jp/box-sorter_data-generator_savetype.py)
- MQTTクライアント
  - ご自身の環境から MQTTブローカーに接続し、メッセージをパブリッシュしたりサブスクライブするのに使用します。
  - お好きなクライアントをご利用ください（:globe_with_meridians:[MQTTX](https://mqttx.app/) など）。

### 商品マスタデータ

- [sorting_condition.csv](./../data/sorting_condition.csv)

### プロジェクトファイル

- [荷物仕分けアプリ (Standard) の実装サンプル（Vantiq 1.34）](./../data/box_sorter_standard_1.34.zip)
- [荷物仕分けアプリ (Standard) の実装サンプル（Vantiq 1.36）](./../data/box_sorter_standard_1.36.zip)

### ドキュメント

- [手順](./instruction.md)
