---
layout: post
title: "(ja) MT4(build 600)のデータフォルダへのシンボリックリンクを一括作成するVBScript"
description: ""
category: mt4
tags: [mt4,tools,japanese]
---
{% include JB/setup %}

MT4 (build 600 とそれ以降) および MT5 のデータフォルダへのシンボリックリンクを作成する VBScript を作成しました。
Windows Vista 以降で利用可能です。

[GitHub](https://github.com/micclly/mt4-tools/blob/master/make-symlinks-to-terminal-data-path.vbs) からダウンロードできます。

MetaTrader 4 (build 600 とそれ以降) および MetaTrader 5 は、EAやインジケータなどをデータフォルダである ``%APPDATA%\MetaQuotes\Terminal\<UNIQUEID>`` に保存します。

特に複数のターミナルを使っている場合、このデータフォルダを開くのが大変です。

この VBScript を実行すると、カレントディレクトリにすべてのデータフォルダへのシンボリックリンクを作成します。
シンボリックリンク名は、データフォルダ直下に存在する origin.txt から決められます。

### 例

- MT4 インストールディレクトリ
    - C:\Program Files\MetaTrader4
- データフォルダ
    - C:\Users\someone\AppData\Roaming\MetaQuotes\Terminal\AAAAABBBBBCCCCC
- 作成されるシンボリックリンク
    - シンボリックリンク名: MetaTrader4
    - リンク先: C:\Users\someone\AppData\Roaming\MetaQuotes\Terminal\AAAAABBBBBCCCCC 
