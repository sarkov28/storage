## https://github.com/contactmodel/COVID19-Japan-Reff のスクリプトを、google colab で動かす
リポジトリ https://github.com/contactmodel/COVID19-Japan-Reff には、西浦氏が公開した実効再生産数の計算などを行うスクリプトがあります。  
このスクリプトは、このままでは google colab で動作しませんが、ある程度修正すると動作します。  
（2023-11-27 の時点で、C は動きません。）

スクリプトは、3つあります。
- A. Showing the epidemic curve.ipynb
- B. Calculating Rt using Maximum likelihood estimation.ipynb  
- C. Calculating the Rt in RStan.ipynb

data フォルダには、これらを動かすためのデータが置いてあります。<br>
（各スクリプトの中には、ここのデータではなく、オリジナルのリポジトリのデータファイルを読んでいるものもあります。）
- JapaneseDataCOVID19 (200510).csv<br>
オリジナルのデータです。
- JapaneseDataCOVID19 (200510)_2.csv, JapaneseDataCOVID19 (200510)_4.csv, JapaneseDataCOVID19 (200510)_8.csv<br>
オリジナルのデータのデータ部分を2倍、4倍、8倍にしたデータです。

