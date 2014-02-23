---
layout: post
title: "(ja) mt4R を MT4 build 600 以降に対応しました"
description: ""
category: mt4
tags: [mt4,mt4r,extension,japanese]
---
{% include JB/setup %}

ちょっと前になりますが、
[mt4R](https://sites.google.com/site/prof7bit/r-for-metatrader-4) を MT4 build 600 以降で
使えるように修正したものを [GitHub](https://github.com/micclly/mt4R) と [CodeBase](http://codebase.mql4.com/9226) で公開しました。

私自身 mt4R は使ったことがなかったのですが、 build 600 になって使えないという声をたまたま見たので、
わりとかなりやっつけで Unicode String 対応をしたものです。

やっつけなので、 DLL 側で受け取った Unicode String を何も考えずに Ansi String に変換しています・・・。

v1.4.0-SNAPSHOT-b6 以降、おそらく問題なく使える状態になっていると思いますので、
build 600 になって mt4R が使えなくて困ってる方は、お試しください。
