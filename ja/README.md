# intdash SDK for Python Samples

intdash SDK for Pythonと他製品を組み合わせた利用例を、サンプルとして提供する実行用ノートブック集です。  


> **注意** :説明で使用している画面は一例です。ご使用の環境やアプリケーションのバージョンによって、表示や手順が一部異なる場合があります。


## 事前準備 

### インストール

以下コマンドでインストールします。

```
$ pip install intdash
```

### クライアントの生成

エッジアカウントの認証情報（ **エッジトークン** 、または **ユーザー名／パスワードの組み合わせ** ）を使用し、クライアントを生成します。

エッジトークン

```
  import intdash

  client = intdash.Client(
	  url = "https://example.intdash.jp",
	  edge_token = "your_token",
  )
```

ユーザー名／パスワード

```
  import intdash

  client = intdash.Client(
      url = "https://hoge.intdash.jp",
      username = "your_username_here",
      password = "your_password_here",
  )
```

### 信号定義の登録
本サンプルコードでは、時系列データの取得時に、信号定義（時系列データを物理値に変換するための定義）を使用するケースがあります。詳しくは `0_create_signals` を参考にしてください。

#### 使用する信号定義の種別

|ケース|信号定義|
|---|---|
|1_save-acquisition-data|汎用センサーデータ型(※) → Float型|
|2_JSON-data-acquisition-using-signal| JSON型 → Float型|
|3_realtime-streaming-execution-processing|汎用センサーデータ型 → Float型|
|4_acquistion-image-data|なし|
|5_create-measurement-markers|汎用センサーデータ型 → Float型|  

(※) 汎用センサー型は、aptpod独自のデータ型であり、今回ではスマートフォンのセンサーデータを示します。

### アプリケーションの準備
本サンプルコードでは、データの伝送およびデータの可視化に、弊社アプリケーションの **Visual M2M** を使用します。詳しくは、各アプリケーションのガイドを確認してください。

- データの伝送：**intdash Motion**
- データの可視化：**Visual M2M Data Visualizer**
