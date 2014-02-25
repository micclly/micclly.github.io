---
layout: post
title: "(ja) build 600 以降での MqlStr について"
description: ""
category: mt4
tags: [mt4,japanese]
---
{% include JB/setup %}

DLL にて MqlStr を使っている場合、
build 600 以降に対応するためには MqlStr の定義を変更する必要があります。

{% highlight cpp %}
struct MqlStr
{
    int len;
    wchar_t* str; // char* から wchar_t* に変更
    int dummy; // 構造体サイズが変わった模様なのでパディング用に追加
};
{% endhighlight %}

MT4 build 600 以降についている、 ``<INSTALL_PATH>/MQL4/Scripts/Examples/DLL/DLLSample.cpp`` にも
MqlStr 構造体は定義されているのですが、これは古いので気を付けてください。

上記の構造体は、 mt4R の build 600 対応時に自分で調査してあたりをつけたものです。

MetaQuotes 公式のものではないので、その点もご留意ください（[フォーラム](http://forum.mql4.com/61293)で質問中です）。
