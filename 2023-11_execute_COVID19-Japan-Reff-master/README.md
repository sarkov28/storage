## https://github.com/contactmodel/COVID19-Japan-Reff のスクリプトを、google colab で動かす
実質的に西浦氏によるリポジトリ https://github.com/contactmodel/COVID19-Japan-Reff には、西浦氏が公開した実効再生産数の計算などを行うスクリプトがあります。  <br>
このスクリプトは、このままでは google colab で動作しませんが、ある程度修正すると動作します。  

スクリプトは、3つあります。
- A. Showing the epidemic curve.ipynb
- B. Calculating Rt using Maximum likelihood estimation.ipynb  
- C. Calculating the Rt in RStan.ipynb

（2023-11-27 の時点で、C は動きません。）

data フォルダには、これらスクリプトで計算する際の入力データが置いてあります。
- JapaneseDataCOVID19 (200510).csv<br>
上に示したリポジトリにもあるオリジナルのデータです。

data_misc フォルダには、オリジナルのデータと、その他のデータが置いてあります。
- JapaneseDataCOVID19 (200510).csv<br>
上に示したリポジトリにあるオリジナルのデータです。
- delay_precalc.csv<br>
"B. Calculating Rt using Maximum likelihood estimation.ipynb" が計算した delay_precalculation のデータです。
- JapaneseDataCOVID19 (200510)_2.csv, JapaneseDataCOVID19 (200510)_4.csv, JapaneseDataCOVID19 (200510)_8.csv<br>
オリジナルのデータのデータ部分を2倍、4倍、8倍にしたデータです。
