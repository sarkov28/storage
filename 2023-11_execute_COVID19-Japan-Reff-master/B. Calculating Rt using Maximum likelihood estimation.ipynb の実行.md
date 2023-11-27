## "B. Calculating Rt using Maximum likelihood estimation.ipynb" を google colab で動かす
"B. Calculating Rt using Maximum likelihood estimation.ipynb" は、西浦氏が github のリポジトリ https://github.com/contactmodel/COVID19-Japan-Reff で公開している（jupyter notebook の）プログラムです。

"B. Calculating Rt using Maximum likelihood estimation.ipynb" は、google colab 上で動かすことができます。
なお、"A. Showing the epidemic curve.ipynb" も動かすことできるのですが、
"C. Calculating the Rt in RStan.ipynb" は現時点では動きません。

google のアカウントでログインしている状態を前提としています。
ログインしていなくても動作するかも知れませんが、確認していません。

#### (1) プログラムファイル
google colab のファイル
https://colab.research.google.com/drive/1ejsmBCplrks1G6CPCkjQMU9icrm1_-kl?usp=sharing
を開きます。
このファイルと、西浦氏が公開しているファイル（2021-11-22 修正版）との相違は、以下です。
- 冒頭のコメント
- 「(2) データファイル」に書いたデータの位置の変更
- 計算モジュール surveillance を（google colab に）インストールする行の追加
- 計算結果ファイルの出力先ディレクトリの変更
- 2021-11-22 の修正にともなうバグを、類似処理と同様の形に修正

このうち最後は、括弧の不対応なので、バグであることは間違いありません。
一方で、私の修正が正しい保証はありません。

バグの修正は以下です。
---- 修正前<br>
for (m in (Start.T-2):max(dt.backproj$t)){<br>
    for (n in 1:(m-1){precal[m-Start.T+2+1,n] <- infectiontoreport(m,n)}}<br>
----<br>
---- sarkov28 による修正<br>
for (m in (Start.T-2):max(dt.backproj$t)){<br>
    for (n in 1:(m-1)){precal[m-Start.T+2+1,n] <- infectiontoreport(m,n)}}<br>
----<br>
上にも書きましたが、「sarkov28 による修正」では、別の類似処理と同じにしています。

#### (2) データファイル
データファイルは、西浦氏が github 上に公開しているものを使います。<br>
https://raw.githubusercontent.com/contactmodel/COVID19-Japan-Reff/master/data/JapaneseDataCOVID19%20(200510).csv<br>
元々のプログラムは、データファイルがファイルがローカルPC上にあることを想定していました。
私が github 上のデータを読むように改変しました。

#### (3) 計算処理
google colab のメニューで [ランタイム] [すべてのセルを実行] を選択すると、計算を行います。
(5)にも関連事項が書いてあります。

計算は、しばらく時間が掛ります。（10～20分掛ると思います。）
このプログラムは、必要な計算モジュールを google colab 上にインストールします。（ユーザーのコンピュータに何かをインストールすることはありません。）
このインストールに長い時間が掛ります。
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
- 2021-11-22 の修正は、（上の私の修正が正しいなら、）出力されたグラフで見る限りは軽微なものでした。

