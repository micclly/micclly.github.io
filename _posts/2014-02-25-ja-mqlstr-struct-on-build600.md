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

上記の構造体は、 [mt4R の build 600 対応時に自分で調査してあたりをつけた](https://github.com/micclly/mt4R/commit/2a604aaf9fef2b054b2d4259d59072a6d9e31215#diff-5) ものです。

MetaQuotes 公式のものではないので、その点もご留意ください（[フォーラム](http://forum.mql4.com/61293)で質問中です）。

-----

## 2014/02/05 追記

フォーラムで聞いた結果、以下のことがわかりました。

- [ドキュメント](http://docs.mql4.com/basis/preprosessor/import) には、以下のように書いている。

> Classes, string arrays or complex objects that contain strings and/or dynamic arrays of any types cannot be passed as a parameter to functions imported from DLL.

- MetaQuotes の人が、[フォーラムで build 600 で MqlStr を使う方法を回答している](http://forum.mql4.com/60555/page20#905209)。

> You should use new struct MqlStr format in the DLL

{% highlight cpp %}
struct MqlStr
  {
   int               len;
   wchar_t          *string;
   int               reserved;
  };
{% endhighlight %}

ということで、ドキュメントには（いまのところ）記載がなく、MT付属のサンプルも間違っているままですが、
上記の構造体を使って string の配列を渡すことは正しい方法のようです。
