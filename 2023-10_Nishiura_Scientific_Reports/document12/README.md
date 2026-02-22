## 2023-10 の西浦氏らの Scientific Reports 論文に関するブログ記事で使う図表
- document12 には、<br>
  （１２）「Figure 1 の一致」の重要性と問題点<br>
  https://sarkov28.hatenablog.com/entry/2026/02/22/121000<br>
  で使う図表を置いています。

- 西浦氏らの論文 [Kayano 2023] は https://doi.org/10.1038/s41598-023-44942-6 です。
- [Kayano 2023] の補足情報は以下などです。<br>
  https://static-content.springer.com/esm/art%3A10.1038%2Fs41598-023-44942-6/MediaObjects/41598_2023_44942_MOESM1_ESM.docx<br>
- [Kayano 2023] の連絡著者の西浦氏は、2025-04-19 に論文に関連するファイル [Nishiura 2025] を以下で公開しました。<br>
  [Nishiura 2025] https://zenodo.org/record/15244462

- [Kayano 2023] の問題点を指摘した、掛谷氏による論文 [Kakeya 2025a] は以下です。<br>
  [Kakeya 2025a] https://zenodo.org/records/17114687<br>
- [Kakeya 2025a] に関する開示情報 [Kakeya 2025b] は以下です。<br>
  [Kakeya 2025b] https://github.com/visual-media-lab/COVID<br>
  ここには、以下が含まれています。
  - 西浦氏による開示情報に含まれていなかった File2 を、掛谷氏が代替的に作成したもの。
  - 西浦氏による開示プログラムには、掛谷氏の論文が指摘する問題がある。この問題を掛谷氏が修正したプログラム。

- [Kakeya 2025b] とは異なる考え方で、File2 の代替データを作成しました。[sarkov28 2026a] です。<br>
  [sarkov28 2026a] https://github.com/sarkov28/storage/tree/3bc9a51d58496f2339164a8bc19514f547e22d3e/2025-12_Kakeya_2025-09
- [sarkov28 2026b] は、[Nishiura 2025] で開示されたプログラムを修正したものです。<br>
  [sarkov28 2026b] https://colab.research.google.com/drive/1MezcBO0m5HDvSCTq_CXMih7rek7461er<br>
  主な修正は以下です。
  - R 言語で書かれた [Nishiura 2025] を、python から rpy2 で R 言語を呼び出すものに修正した。
  - google colab で動作するようにライブラリ読み込みを追加した。
  - データファイルを、ネット上から読み込む用に修正した。
  - loop 外に出すことができる計算などを修正し、高速化した。[Nishiura 2025] で1時間程度を要していた計算を、13分～30秒程度で行えるようになった。

