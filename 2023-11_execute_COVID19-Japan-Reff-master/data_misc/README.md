## https://github.com/contactmodel/COVID19-Japan-Reff のスクリプトを、google colab で動かす
実質的に西浦氏によるリポジトリ https://github.com/contactmodel/COVID19-Japan-Reff には、西浦氏が公開した実効再生産数の計算などを行うスクリプトがあります。<br>

このフォルダには、これらスクリプトで計算する際の入力データが置いてあります。
- JapaneseDataCOVID19_(200510).csv<br>
  上に示したリポジトリにあるオリジナルのデータです。<br>
  ファイル名を、"JapaneseDataCOVID19 (200510).csv" から "JapaneseDataCOVID19_(200510).csv" に変更しました。
- delay_precalc.csv<br>
  "B. Calculating Rt using Maximum likelihood estimation.ipynb" が計算した delay_precalculation のデータです。
- JapaneseDataCOVID19_(200510)_2.csv, JapaneseDataCOVID19_(200510)_4.csv, JapaneseDataCOVID19_(200510)_8.csv<br>
  オリジナルのデータのデータ部分を2倍、4倍、8倍にしたデータです。
- JapaneseDataCOVID19_(200510)_count1.csv<br>
  JapaneseDataCOVID19_(200510).csv のデータを、onset, confirmed, reported の日付毎に集計したもの。
- JapaneseDataCOVID19_(200510)_count2.csv<br>
  JapaneseDataCOVID19_(200510).csv のデータを、imported, domestic 毎、onset, confirmed, reported の日付毎に集計したもの。
