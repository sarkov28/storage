## https://github.com/contactmodel/COVID19-Japan-Reff のスクリプトを、google colab で動かす
実質的に西浦氏によるリポジトリ https://github.com/contactmodel/COVID19-Japan-Reff には、西浦氏が公開した実効再生産数の計算などを行うスクリプトがあります。<br>

このフォルダには、これらスクリプトで計算する際の入力データや、関連するデータが置いてあります。<br>
<br>
入力用のデータ:
- JapaneseDataCOVID19_(200510).csv<br>
  上に示したリポジトリにあるオリジナルのデータです。<br>
  ファイル名を、"JapaneseDataCOVID19 (200510).csv" から "JapaneseDataCOVID19_(200510).csv" に変更しました。
- JapaneseDataCOVID19_(200510)\_a0.csv
  オリジナルのデータから、is_asymptomatic == 0 の case だけを抜き出したもの。
- JapaneseDataCOVID19_(200510)\_2.csv, JapaneseDataCOVID19_(200510)\_4.csv, JapaneseDataCOVID19_(200510)\_8.csv<br>
  オリジナルのデータのデータ部分を2倍、4倍、8倍にしたデータです。

西浦氏のプログラムによるグラフ:
- 2020-05-10_github_calcRt_org_B_2020-05-10_fig.1.png<br>
  プログラム B の1枚目のグラフです。
- 2020-05-10_github_calcRt_org_B_2020-05-10_fig.2.png<br>
  プログラム B の2枚目のグラフです。
- 2020-05-10_github_calcRt_org_C_2020-05-10_fig.1.png<br>
  プログラム C のグラフです。

西浦氏のプログラム B を私が改変したプログラムによるグラフ:
- 2020-05-10_github_calcRt_B_2020-05-10_fig.2.png<br>
  プログラム B の1枚目のグラフです。

その他のデータ:
- JapaneseDataCOVID19_(200510)\_count1.csv<br>
  JapaneseDataCOVID19_(200510).csv を、onset, confirmed, reported の日付毎に集計したものです。
- JapaneseDataCOVID19_(200510)\_count2.csv<br>
  JapaneseDataCOVID19_(200510).csv を、imported, domestic 毎、onset, confirmed, reported の日付毎に集計したものです。
- delay_precalc.csv<br>
  "B. Calculating Rt using Maximum likelihood estimation.ipynb" が計算する delay_precalculation(t) の、1 <= t <= 127 での値です。
- delay_precalc.png<br>
  delay_precalc.csv の グラフです。
- delay_precalc_rev.csv<br>
  delay_precalc.csv の横軸を反転したものです。
- delay_precalc_rev.png<br>
  delay_precalc_rev.csv のグラフです。

