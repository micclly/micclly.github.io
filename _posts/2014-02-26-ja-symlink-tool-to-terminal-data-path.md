---
layout: post
title: "(ja) MT4(build 600)のTerminal Data Pathへのシンボリックリンクを一括作成するVBScript"
description: ""
category: mt4
tags: [mt4,tools,japanese]
---
{% include JB/setup %}

MT4 (build 600 とそれ以降) および MT5 の Terminal Data Path へのシンボリックリンクを作成する VBScript を作成しました。
Windows Vista 以降で利用可能です。

[GitHub](https://github.com/micclly/mt4-tools/blob/master/make-symlinks-to-terminal-data-path.vbs) からダウンロードできます。

MetaTrader 4 (build 600 とそれ以降) および MetaTrader 5 は、EAやインジケータなどを ``%APPDATA%\MetaQuotes\Terminal\<UNIQUEID>`` に保存します（これを Terminal Data Path といいます）。

特に複数のターミナルを使っている場合、このディレクトリを開くのが大変です。

この VBScript を実行すると、カレントディレクトリにすべての Terminal Data Path へのシンボリックリンクを作成します。
シンボリックリンク名は、Terminal Data Path 直下に存在する origin.txt から決められます。

### 例

- MT4 インストールディレクトリ
    - C:\Program Files\MetaTrader4
- Terminal Data Path
    - C:\Users\someone\AppData\Roaming\MetaQuotes\Terminal\AAAAABBBBBCCCCC
- 作成されるシンボリックリンク
    - シンボリックリンク名: MetaTrader4
    - リンク先: C:\Users\someone\AppData\Roaming\MetaQuotes\Terminal\AAAAABBBBBCCCCC 
