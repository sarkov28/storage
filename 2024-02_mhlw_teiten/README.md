## 厚労省のインフルエンザとコロナの週次の定点データのグラフ化

### （１）データの所在
グラフ作成時点での最新のデータを以下の要領で入手した。<br>

以下の url にある、「定点把握疾患（週報告）、（１週から当該週まで）報告数・定点当り報告数」のデータを入手した。

- 2023年の分<br>
2023年最終週である、2023年第52週のデータ。<br>
https://www.niid.go.jp/niid/ja/data/12442-idwr-sokuho-data-j-2352.html<br>
の「定点把握疾患（週報告）、（１週から当該週まで）報告数・定点当り報告数」。<br>
ファイルパス名：https://www.niid.go.jp/niid/images/idwr/sokuho/idwr-2023/202352/2023-52-teiten-tougai.csv
- 2024年の分<br>
グラフ作成時点の最終週、2024年第6週のデータ。<br>
https://www.niid.go.jp/niid/ja/data/12519-idwr-sokuho-data-j-2406.html<br>
の「定点把握疾患（週報告）、（１週から当該週まで）報告数・定点当り報告数」。<br>
ファイルパス名：https://www.niid.go.jp/niid/images/idwr/sokuho/idwr-2024/202406/2024-06-teiten-tougai.csv

### （２）作成したグラフと、グラフ作成に用いたデータ
（１）で入手したデータから週次の定点のデータを抜き出したファイルを作成し、グラフを作成した。

- graph_Chiba_flu_c19<br>
確認用に作成した、厚労省ページと似た体裁のグラフ。
- graph_47_flu.png<br>
千葉県と他の都道府県のインフルエンザのグラフ。
- graph_47_c19.png<br>
千葉県と他の都道府県の新型コロナのグラフ。
- data_47_flu_sjis.csv と data_47_flu_utf8.csv<br>
インフルエンザのデータ。文字コードが前者は shift-jis。後者は utf8。
- data_47_c19_sjis.csv と data_47_c19_utf8.csv<br>
新型コロナのデータ。文字コードが前者は shift-jis。後者は utf8。

