
# 図書管理システム（アプリ開発に関する研究）


# 1.　背景

第一工業大学東京キャンパスの研究室に、たくさん図書資料があり、各研究室の本棚に分散し、紙リストで各自管理している。本と管理表が一致しない場合がある。もし本のリストがクラウドで一元管理でき、スマートフォンで簡単に検索、管理できれば、資料の有効活用ができ、管理者利用者に沢山メリットをもたらす。

# 2.　目的

本研究は、クラウドとスマートフォンアプリを連携して図書資料管理システムを作り、いつでも、どこでも、本の情報を入手し、具体的な置く場所の情報を手に入れる。また図書資料の有効活用も促進する。

# 3.　研究内容・方法

## （１）研究内容

図書管理システムはクラウドとスマートフォンアプリで構成される。図書管理システムのクラウドには、たくさんの図書と、複数の図書を一括管理する本棚が設ける。研究室ことに、複数の本棚が設ける。図書は本棚のコード（バーコード）と図書のISBN（バーコード）の組み合わせで管理する。アプリはバーコードスキャン方法で入力の手間を省け、入力ミスを防げ、簡単に利用できる。

私はスマートフォンアプリ側の研究担当である。

スマートフォンアプリは、以下の機能を実装する予定
①表紙をデザインする。
　②図書バーコードスキャンし、図書検索する。
③クラウドAPIに接続し、図書データ取得
④本棚を作成し、バーコードで管理する。
⑤図書登録し、図書を本棚に登録する。

## (2) 研究方法

①デザイン
図書管理システムのはメイン画面、検索画面、本棚画面で構成され、図１は図書管理システムの構成図である。

![](./image1.png)

図１

## ②プログラミング

App InventorはMITが提供していたAndroid対応アプリケーションを開発するソフトウェアである。難解な開発言語を覚える必要はない。パズルを作り上げていくようにアプリケーションを作成することができる。
ウェブサーバーにデータを取得するために、APIを利用する。図２に示した通り、TinyWebDBという部品を使えば簡単にできる。TinyWebDBはタグをつけてメッセージをクラウドに保存したり、サーバーにタグ名を送信してその値を受け取ったりすることができる。

本システムはApp Inventorを用いて図書管理システムを開発する。TinyWebDBのServiceURLを（http://tinydb.host/xulei/api）に設定する。本のISBNをタグとしてクラウドに送り、クラウドから本の詳細データが受けとれる。

![](./image2.png)

図２



実際のプログラムが図３の示した通り。

![](./image3.png)

図３


## ③実演

アプリを立ち上がると図４左はメイン画面で「検索」と「研究室一覧」ボタンがついている。
　「検索」は検索画面を呼び出すボタンで、「研究室一覧」は研究室一覧リストへ遷移するボタンである。
「研究室一覧」は本棚画面へ遷移するボタンである。
図４右は本棚画面で、スマートフォンに作った本棚である。


![](./image5.png)

図４


図５は検索結果が本棚に入れる。最初のQRアイコンを押して、スキャンモードに入り、本のバーコードを数字の形でTextBookに読み取れる。


![](./image6.png)

図５

検索ボタンをクリックして、検索結果が出る。もし、この本が好きならば、本棚に入れるボタンをクリックすると、本棚に入れる。本棚で本を削除したいときに、本の表紙を長押しして、削除ができる。

# 4.　結果・考察

本研究は、クラウドとスマートフォンアプリを連携して、いつでも、どこでも、本研究室に本の情報を入手した。
具体的な置く場所の情報を本棚コードとしてTextBoxに表示した。
スマートフォンに保存された画像も一緒に表示し、図５のように検索した本が本棚リスト（スマートフォン用）に登録した。紙管理が一元化（デジタル化）になり、わかりやすく管理する。利用者に資料の有効活用ができる研究を行なっていた。
但し、クラウドの本棚とアプリの本棚を同期できない、そしてクラウドから本の表紙を取り込みできない.

# 5.　結論

このアプリを使っていれば、効率が上がる。本もきれいな本棚に並べて、見やすく、便利になっている。
今後の課題として、クラウドの本棚とアプリの本棚を同期する仕組み、そしてクラウドから本の表紙を取り込みする機能を実装する。






