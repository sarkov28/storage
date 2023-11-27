## "A. Showing the epidemic curve.ipynb" を google colab で動かす
"A. Showing the epidemic curve.ipynb" は、西浦氏が github のリポジトリ https://github.com/contactmodel/COVID19-Japan-Reff で公開している（jupyter notebook の）プログラムです。

"A. Showing the epidemic curve.ipynb" と同じ結果と思われるものを、google colab 上で得ることができます。
なお、"B. Calculating Rt using Maximum likelihood estimation.ipynb" も動かすことできるのですが、
"C. Calculating the Rt in RStan.ipynb" は現時点では動きません。

google のアカウントでログインしている状態を前提としています。
ログインしていなくても動作するかも知れませんが、確認していません。

#### (1) プログラムファイル
google colab のファイル
https://colab.research.google.com/drive/1pnG09AcFwPVzilBwrPfzcJu3l1sH_Vi4?usp=drive_link
を開きます。
このファイルと、（西浦氏が公開した）オリジナルとの相違は、以下です。
- 冒頭のコメント
- 「(2) データファイル」に書いたデータの位置の変更

#### (2) データファイル
データファイルは、西浦氏が github 上に公開しているものを使います。<br>
https://raw.githubusercontent.com/contactmodel/COVID19-Japan-Reff/master/data/JapaneseDataCOVID19%20(200510).csv<br>
元々のプログラムは、データファイルがファイルがローカルPC上にあることを想定していました。
（この想定だと、データファイルを google colab に（毎回）アップロードしないと動作しないため、）私は、github 上のデータを読むように改変しました。

#### (3) 計算処理
google colab のメニューで [ランタイム] [すべてのセルを実行] を選択すると、計算を行います。
(5)にも関連事項が書いてあります。

計算は、しばらく時間が掛りますが、数分程度で終わります。

#### (4) 結果
手元で実行したところ、以下が得られました。
- "Cases with known date of illness onset" のグラフ。（下から1/3程の位置）
- "Cases with unknown date of illness onset" のグラフ。（ほぼ一番下。）

#### (5) 留意事項
- 再実行する前に出力をクリアするには、[編集] メニューの [出力を全て消去] を選択して下さい。
  通常は、これを行う必要はありません。
- 全てのセルを実行するには、[ランタイム] メニュー [すべてのセルを実行] を選択して下さい。
- 何か修正を行って、再実行する場合は、[ランタイム] [再起動してすべてのセルを実行] を選択する方がいいかも知れません。
google colab の使い方の詳細は、別途お調べ頂いた方がいいと思います。

