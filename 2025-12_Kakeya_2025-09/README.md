# （１）概要
西浦氏が「ワクチンなし」での死者数などを計算したと主張する反実仮想シナリオ論文 [\[Kayano 2023\]] の再現計算は、（[\[Nishiura 2025\]] で File2 が不開示だったために）最後まで行うことはできませんでした。[\[Kakeya 2025a\]] は File2 の代替データを作成し、再現計算を行い、[\[Kayano 2023\]] の Figure 1 などの計算の問題点を指摘しています。

このフォルダには、私が（幾らか異なる考え方で）作成した File2 の代替データを置いています。

<a href="https://raw.githubusercontent.com/sarkov28/storage/master/2025-12_Kakeya_2025-09/Kayano_et_al-2023-Scientific_Reports_Fig_1_with_hdr.png"><img src="https://raw.githubusercontent.com/sarkov28/storage/master/2025-12_Kakeya_2025-09/Kayano_et_al-2023-Scientific_Reports_Fig_1_with_hdr.png" width="400px" alt="[Kayano 2023] の Figure 1"></a><br>

# （２）西浦教授の論文 [\[Kayano 2023\]] と開示情報 [\[Nishiura 2025\]] について
京都大学大学院の西浦教授らによる [\[Kayano 2023\]] は、「ワクチンなし」での感染者数や死者数を反実仮想シナリオを用いて計算したと主張する論文です。この論文で用いられたプログラムやデータは論文発表（2023-10）からしばらくの間不開示でしたが、西浦教授は 2025-04 に zenodo [\[Nishiura 2025\]] で一部を開示しました。

# （３）File2、[\[Kakeya 2025b\]] で示された代替データ、西浦氏の論文の問題点について
[\[Nishiura 2025\]] では File2 が開示されませんでした。開示プログラムの主たる部分を動作させるには File2 が必要です。筑波大学の掛谷准教授は論文 [\[Kakeya 2025a\]] とその開示情報 [\[Kakeya 2025b\]] で、File2 を代替するデータを示しました。また、[\[Kayano 2023\]] の計算の問題点を指摘しました。

[\[Kakeya 2025a\]] は、問題点の中核を簡潔に述べているため、分かりにくいかもしれません。私は、[\[sarkov28 2026a\]] の（５）節 に、この付近に関するある程度の説明を示しました。

# （４）[\[Nishiura 2025\]] の開示プログラムの計算を高速化したプログラムについて
ここにある代替データを用いれば、[\[Nishiura 2025\]] の開示プログラムを計算できます。しかしこの計算はかなり時間を要するものであり、Google Colab での実行では、1つの reporting coverage の計算に1時間程度を要します。（開示プログラムの仕様上、4つの reporting coverage (=1, 0.5, 0.25, 0.125) で計算するにはパラメータを変更しながら計算を4回行うことになります。これには4時間程度を要します。）

開示プログラムには、loop の中で繰り返す必要のない計算を行うなどの高速化余地がありました。私は開示プログラムの内容を高速計算する [\[sarkov28 2026b\]] を示しています。これを用いると、初回の計算は12分程度、2回目以降は30秒程度で計算できるので、4つの reporting coverage での計算を15分程度で行うことができます。高速化したプログラムと開示プログラムとの計算結果には、丸め誤差と思われる差異がありますが、グラフの視覚上における差異はないと考えています。

# （５）ここにある代替データについて
## (5-1) File2_v3 のデータを用いるのが適切と考える理由
[\[Nishiura 2025\]] が開示していない File2 の代替データとしては、3つ（[\[Kakeya 2025b\]] のもの、ここにある v2、ここにある v3）があります。これらについて先日までは、「どれを用いるかについての定量的な確認はしていない」旨を書いていました。現在でも、[\[Kayano 2023\]] の Figure 1 の再現においてはどれを用いても大差がないと考えています。（Figure 1 の再現は、[\[Nakamura 2024\]] の開示プログラムの "# 4" の 1つ目の ggplot() です。）

一方で最近分かった事情により、あるグラフの再現に関しては v3 の使用が適切だと考えています。それは [\[Kayano 2023\]] の Figure 2A です（開示プログラムの "# 7" の1つ目のggplot() です）。このグラフの再現で [\[Kakeya 2025b\]] や v2 の代替File2 を用いると、視覚的に明確な違いがあります。一方で v3 を用いると（やや違いはありますが）ある程度類似したグラフが得られます。

(5-1)節 に述べた事情は、[\[Kakeya 2025b\]] の論旨に影響しません。[\[Kakeya 2025b\]] が検討しているのは [\[Kayano 2023\]] の Figure 1 であり、Figure 2A ではないからです。

<a href="https://raw.githubusercontent.com/sarkov28/storage/master/2025-12_Kakeya_2025-09/Kayano_et_al-2023-Scientific_Reports_Fig_2A_with_hdr.png"><img src="https://raw.githubusercontent.com/sarkov28/storage/master/2025-12_Kakeya_2025-09/Kayano_et_al-2023-Scientific_Reports_Fig_2A_with_hdr.png" width="300px" alt="[Kayano 2023] の Figure 2A"></a><br>

## (5-2) File2_v2 にある代替データについて
v2 にある代替データは、[\[Kayano 2023\]] の Figure 1 の各日付のオレンジ点の座標値を私（x.com/sarkov28）が ChatGPT を使って読み取った結果から作成しました。Figure 1 のオレンジ点は、全年齢群の新規感染者数の合計値です。**10個の各年齢群の新規感染者数は等しいと仮定** して処理しました。したがって各年齢群の各データは全て、(オレンジ点の座標値)/10 の値です [注5-2]。

v2 のデータは、私が確認した限りでは、[\[Kakeya 2025b\]] のデータよりも Figure 1 のオレンジ点をよく再現しています。ただしこの差異が計算結果にどのように影響するかの定量的な確認は、今のところ行っていません。なおそもそも [\[Kakeya 2025b\]] の代替データを使った計算は、[\[Kayano 2023\]] の Figure 1 をよく再現しています（[\[Kakeya 2025a\]] の Figure 1 の左）。

[注5-2] 読み取った座標値は、v2 のデータの cases のカラムにあります。ただし、Figure 1 のデータ開始は 2021-02-17 ですが、計算には少なくとも14日前までのデータが必要なので、2021-02-03～2021-02-16 のデータを（Figure 1 の座標読み取り以外の方法で）作成する必要があります。今回はこれを「2021-02-17 の座標値と同じ値である」との考え方で作成しました。この考え方は、おそらく [\[Kakeya 2025b\]] も採用しているものです。

## (5-3) File2_v3 にある代替データについて
v3 にある代替データは、v2 のデータを改良したものです。**v2 では、10個の各年齢群の新規感染者数は等しいと仮定** して処理しました。**v3 ではこれが各年齢群ごとに異なると仮定** しました。

年齢群ごとのデータは、（日別ではなく）週別ではありますが厚労省が発表しているので、v3 ではこれを使いました。[\[mhlw 2023a\]] の [\[mhlw 2023b\]] 「性別・年代別新規陽性者数（週別）」です。

このデータは報告日基準のデータなので、感染日基準への変換として「データの日付から一律に7日減算」の簡易処理を行いました [注5-3-1]。その上で、各日付の年齢群のデータの比率が、厚労省データの（該当する日付の）年齢群の比率に等しくなるように v2 を調整したのが、v3 です。

v2 よりも v3 の方が [\[Kayano 2023\]] が使用したデータに近いだろうと思われます。(5-1)節 に述べた事情があるので、v2 よりは v3 を用いるのが適切だと考えています。

[注5-3-1] 報告遅れを7日とした根拠は以下です。[\[Kayano 2023\]] は、感染から発症までの遅れを平均 4.6 日、発症から報告までの遅れを平均 2.6 日としています。ここで得たいのは感染から報告までの遅れですから、この合計を計算して 4.6 + 2.6 = 7.2 とし、これを整数に丸め、7 を得ました。なお、論文が報告遅れを確率分布として表現し、surveillance による逆計算で感染日を得たと述べているところ、v3 作成で採用したのは「一律に7日を減算する」という、より簡易な処理方法です。

# （６）論文 [\[Kayano 2023\]] への他の疑義
[\[Kakeya 2024\]] は [\[Kayano 2023\]] のパラメータの信頼性の低さなどを指摘し、[\[Nakamura 2024\]] は数理モデルの数学的不正確さなどを指摘しています。私は [\[sarkov28 2024\]] で、[\[Kayano 2023\]] の計算は非現実的な状況を計算したものだと指摘していますが、ここではとりあえずこの疑問は措いて、Figure 1 の観測値と予測値の一致に関する問題を検討しました。また [\[sarkov28 2025\]] では、[\[Nishiura 2025\]] の開示プログラムが論文のグラフの一部を再現しない件について述べました。

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
[sarkov28 2026a] https://sarkov28.hatenablog.com/entry/2026/02/22/121000<br>
[sarkov28 2026b] https://colab.research.google.com/drive/1MezcBO0m5HDvSCTq_CXMih7rek7461er<br>

[\[Kakeya 2024\]]: https://doi.org/10.1101/2024.02.02.24302123
[\[Kakeya 2025a\]]: https://zenodo.org/records/17114687
[\[Kakeya 2025b\]]: https://github.com/visual-media-lab/COVID
[\[Kayano 2023\]]: https://doi.org/10.1038/s41598-023-44942-6
[\[mhlw 2023a\]]: https://covid19.mhlw.go.jp/extensions/public/index.html
[\[mhlw 2023b\]]: https://covid19.mhlw.go.jp/public/opendata/newly_confirmed_cases_detail_weekly_old.csv
[\[Nakamura 2024\]]: http://dx.doi.org/10.13140/RG.2.2.12968.99840/1
[\[Nishiura 2025\]]: https://zenodo.org/records/15244462
[\[sarkov28 2024\]]: https://sarkov28.hatenablog.com/entry/2024/12/17/184600
[\[sarkov28 2025\]]: https://sarkov28.hatenablog.com/entry/2025/05/27/163000
[\[sarkov28 2026a\]]: https://sarkov28.hatenablog.com/entry/2026/02/22/121000
[\[sarkov28 2026b\]]: https://colab.research.google.com/drive/1MezcBO0m5HDvSCTq_CXMih7rek7461er

