---
layout: post
title: "(ja) MT4 build 600以降用スクリプト呼び出しライブラリ"
description: ""
category: mt4
tags: [mt4,library,japanese]
---
{% include JB/setup %}

build 509 以前の MT4 では、[この方法で](http://forum.mql4.com/20946) インジケータやEAからスクリプトを呼び出すことが
できたようです。

某所の書き込みにて、build 600 では上記の方法が使えないようだという情報を目にしたため、
実際に自分でも ``SetWindowHookEx`` を使ってメッセージをフックしてみたところ、
たしかに ``wParam``, ``lParam`` ともにパラメータ値が変更になっているようでした。

build 600 以降では ``wParam`` に 0x11(17) を、
``lParam`` にツリービューのスクリプトの並びの序数（一番上のスクリプトが0）
を指定することで、スクリプトが呼び出せるようでしたので、
DLL と MQL クラスライブラリを試しに作ってみました。

[GitHub](https://github.com/micclly/mt4-script-caller) ([zipはここから](https://github.com/micclly/mt4-script-caller/releases)) 上で公開していますので、必要な方はご利用ください。

使い方は [README.md](https://github.com/micclly/mt4-script-caller/blob/master/README.md) をよくお読みくださいませ。

