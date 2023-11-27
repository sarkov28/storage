## "B. Calculating Rt using Maximum likelihood estimation.ipynb" を google colab で動かす
"B. Calculating Rt using Maximum likelihood estimation.ipynb" は、西浦氏が github のリポジトリ https://github.com/contactmodel/COVID19-Japan-Reff で公開している（jupyter notebook の）プログラムです。

"B. Calculating Rt using Maximum likelihood estimation.ipynb" は、google colab 上で動かすことができます。
なお、"A. Showing the epidemic curve.ipynb" も動かすことできるのですが、
"C. Calculating the Rt in RStan.ipynb" は現時点では動きません。

google のアカウントでログインしている状態を前提としています。
ログインしていなくても動作するかも知れませんが、確認していません。

#### (1) プログラムファイル
google colab のファイル
https://colab.research.google.com/drive/1HimDQe9MSaQRwwmtvPD1I82d-2UeaAxP?usp=drive_link
を開きます。

#### (2) データファイル
データファイルは、西浦氏が github 上に公開しているものを使います。
元々のプログラムは、データファイルがファイルがローカルPC上にあることを想定していました。
私が github 上のデータを読むように改変しました。

#### (3) 計算処理
google colab のメニューで [ランタイム] [すべてのセルを実行] を選択すると、計算を行います。
(5)にも関連事項が書いてあります。

計算は、しばらく時間が掛ります。（10～20分掛ると思います。）
このプログラムは、google colab の標準ではない計算モジュールを google colab 上にインストールします。（ユーザーのコンピュータに何かをインストールすることはありません。）
この時間が長いのが主因です。
（インストール作業以外の）計算本体も、しばらくかかります。

#### (4) 結果
手元で実行したところ、以下が得られました。
- "Entire Japan" のグラフ。（下から1/3程の位置）
- "Entire Japan excluding unknown cases" のグラフ。（ほぼ一番下。）
- google colab の「ファイル」領域に、2つの結果ファイル。"rtmle.csv" と、"rtwcmle.csv"。
なお、google colab の「ファイル」領域のファイルは、google colab をしばらく放置していると、削除されます。これは google colab の仕様です。課金すればこの状況を改善できるようですが、詳細は別途お調べ頂いた方がいいと思います。

#### (5) 留意事項
- 再実行する前に出力をクリアするには、[編集] メニューの [出力を全て消去] を選択して下さい。
  通常は、これを行う必要はありません。
- 全てのセルを実行するには、[ランタイム] メニュー [すべてのセルを実行] を選択して下さい。
- 何か修正を行って、再実行する場合は、[ランタイム] [再起動してすべてのセルを実行] を選択する方がいいかも知れません。
google colab の使い方の詳細は、別途お調べ頂いた方がいいと思います。
- 一部のセルの実行で警告メッセージが出ますが、手元で実行した際については、全体は正常終了したと思われます。

