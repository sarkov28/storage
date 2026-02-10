# （１）概要
西浦氏が「ワクチンなし」での死者数などを計算したと主張する反実仮想論文 [\[Kayano 2023\]] の再現計算は、（[\[Nishiura 2025\]] で File2 が不開示だったために）最後まで行うことはできませんでした。[\[Kakeya 2025a\]] は File2 の代替データを作成し、再現計算を行い、[\[Kayano 2023\]] の Figure 1 などの計算の問題点を指摘しています。

このフォルダには、私が（幾らか異なる考え方で）作成した File2 の代替データを置いています。特に問題を感じていなければ、ここにおいたファイルを使う必要はないかも知れません。

<a href="https://raw.githubusercontent.com/sarkov28/storage/master/2025-12_Kakeya_2025-09/Kayano_et_al-2023-Scientific_Reports_Figure_1_title.png"><img src="https://raw.githubusercontent.com/sarkov28/storage/master/2025-12_Kakeya_2025-09/Kayano_et_al-2023-Scientific_Reports_Figure_1_title.png" width="400px" alt="[Kayano 2023] の Figure 1"></a><br>

# （２）西浦教授の論文 [\[Kayano 2023\]] と開示情報 [\[Nishiura 2025\]] について
京都大学大学院の西浦教授らによる [\[Kayano 2023\]] は、「ワクチンなし」での感染者数や死者数を反実仮想シナリオを用いて計算したと主張する論文です。この論文で用いられたプログラムやデータは論文発表（2023-10）からしばらくの間不開示でしたが、西浦教授は 2025-04 に zenodo [\[Nishiura 2025\]] で一部を開示しました。

# （３）File2 や、[\[Kakeya 2025b\]] で示された代替データについて
[\[Nishiura 2025\]] では File2 が開示されませんでした。開示プログラムの主たる部分を動作させるには File2 が必要です。筑波大学の掛谷准教授は論文 [\[Kakeya 2025a\]] とその開示情報 [\[Kakeya 2025b\]] で、File2 を代替するデータを示すと共に、[\[Kayano 2023\]] の計算の問題点を指摘しました。

# （４）ここにある代替データについて
## (4-1) v2 にある代替データについて
v2 にある代替データは、[\[Kayano 2023\]] の Figure 1 の各日付のオレンジ点の座標値を私（x.com/sarkov28）が ChatGPT を使って読み取った結果から作成しました。Figure 1 のオレンジ点は、全年齢群の新規感染者数の合計値です。**10個の各年齢群の新規感染者数は等しい** と仮定して処理しました。したがって各年齢群の各データは全て、(オレンジ点の座標値)/10 の値です [*4-1]。

v2 のデータは、私が確認した限りでは、[\[Kakeya 2025b\]] のデータよりも Figure 1 のオレンジ点をよく再現しています。ただしこの差異が計算結果にどのように影響するかの定量的な確認は、今のところ行っていません。なおそもそも [\[Kakeya 2025b\]] の代替データを使った計算は、[\[Kayano 2023\]] の Figure 1 をよく再現しています（[\[Kakeya 2025a\]] の Figure 1 の左）。私は、v2 のデータを使う必然性があると言いたいのではありません。

[*4-1] 読み取った座標値は、v2 のデータの cases のカラムにあります。ただし、Figure 1 のデータ開始は 2021-02-17 ですが、計算には少なくとも14日前までのデータが必要なので、2021-02-03～2021-02-16 のデータを（Figure 1 の座標読み取り以外の方法で）作成する必要があります。今回はこれを「2021-02-17 の座標値と同じ値である」との考え方で作成しました。この考え方は、おそらく [\[Kakeya 2025b\]] も採用しているものです。

## (4-2) v3 にある代替データについて
v3 にある代替データは、v2 のデータを改良したものです。v2 では、**10個の各年齢群の新規感染者数は等しい** と仮定して処理しました。v3 ではこれが **各年齢群ごとに異なる** と仮定しました。<br>

年齢群ごとのデータは、（日別ではなく）週別ではありますが厚労省が発表しているので、v3 ではこれを使いました。[\[mhlw 2023a\]] の [\[mhlw 2023b\]] 「性別・年代別新規陽性者数（週別）」です。
<br>
このデータは報告日基準のデータなので、感染日基準への変換として「データの日付から一律に7日減算」の処理を行いました [*4-2-1]。<br>
その上で、各日付の年齢群のデータの比率が、厚労省データの（該当する日付の）年齢群の比率に等しくなるように v2 を調整したのが、v3 です。

v2 よりも v3 の方が [\[Kayano 2023\]] が使用したデータに近いだろうと思われます。ただし v2 と v3 の差異が計算結果にどのように影響するかの定量的な確認は、今のところ行っていません。

[*4-2-1] 報告遅れを7日とした根拠は以下です。[\[Kayano 2023\]] は、感染から発症までの遅れを平均 4.6 日、発症から報告までの遅れを平均 2.6 日としています。ここで得たいのは感染から報告までの遅れですから、この合計を計算して 4.6 + 2.6 = 7.2 とし、これを整数に丸め、7 を得ました。なお、論文が報告遅れを確率分布として表現し、surveillance による逆計算で感染日を得たと述べているところ、v3 作成で採用したのは「一律に7日を減算する」という、より簡易な処理方法です。

# （５）論文 [\[Kayano 2023\]] への他の疑義
[\[Kakeya 2024\]] は [\[Kayano 2023\]] のパラメータの信頼性の低さなどを指摘し、[\[Nakamura 2024\]] は数理モデルの数学的不正確さなどを指摘しています。私は [\[sarkov28 2024\]] で、[\[Kayano 2023\]] の計算は非現実的な状況を計算したものだと指摘していますが、ここではとりあえずこの疑問は措いて、Figure 1 の観測値と予測値の一致に関する問題を検討しました。また、[\[sarkov28 2025\]] では、[\[Nishiura 2025\]] の開示プログラムが論文のグラフの一部を再現しない件について述べました。

# 参考文献
[Kakeya 2024] https://doi.org/10.1101/2024.02.02.24302123<br>
[Kakeya 2025a] https://zenodo.org/records/17114687<br>
[Kakeya 2025b] https://github.com/visual-media-lab/COVID<br>
[Kayano 2023] https://doi.org/10.1038/s41598-023-44942-6<br>
[mhlw 2023a] https://covid19.mhlw.go.jp/extensions/public/index.html<br>
[mhlw 2023b] https://covid19.mhlw.go.jp/public/opendata/newly_confirmed_cases_detail_weekly_old.csv<br>
[Nakamura 2024] http://dx.doi.org/10.13140/RG.2.2.12968.99840/1<br>
[Nishiura 2025] https://zenodo.org/records/15244462<br>
[sarkov28 2024] https://sarkov28.hatenablog.com/entry/2024/12/17/184600<br>
[sarkov28 2025] https://sarkov28.hatenablog.com/entry/2025/05/27/163000<br>

[\[Kakeya 2024\]]: https://doi.org/10.1101/2024.02.02.24302123
[\[Kakeya 2025a\]]: https://zenodo.org/records/17114687
[\[Kakeya 2025b\]]: https://github.com/visual-media-lab/COVID
[\[Kayano 2023\]]: https://doi.org/10.1038/s41598-023-44942-6
[\[mhlw 2023a\]]: https://covid19.mhlw.go.jp/extensions/public/index.html
[\[mhlw 2023b\]]: https://covid19.mhlw.go.jp/public/opendata/newly_confirmed_cases_detail_weekly_old.csv<
[\[Nakamura 2024\]]: http://dx.doi.org/10.13140/RG.2.2.12968.99840/1
[\[Nishiura 2025\]]: https://zenodo.org/records/1524446
[\[sarkov28 2024\]]: https://sarkov28.hatenablog.com/entry/2024/12/17/184600
[\[sarkov28 2025\]]: https://sarkov28.hatenablog.com/entry/2025/05/27/163000

