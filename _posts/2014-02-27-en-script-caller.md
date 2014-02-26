---
layout: post
title: "(en) Script Calling Library for MT4 build 600 and later"
description: ""
category: mt4
tags: [mt4,library,english]
---
{% include JB/setup %}

On earlier build of MT4, script can be called from indicator and experts,
with [this method](http://forum.mql4.com/20946).

From build 600, ``wParam`` and ``lParam`` of ``MetaTrader4_Internal_Message``
has been changed.

Now wParam is 0x11, and lParam is the ordinal in the Navigator tree view, which starts from 0 (upside is origin).

I've created a DLL and it's MQL class library. You can get from [GitHub](https://github.com/micclly/mt4-script-caller) (zip is from [here](https://github.com/micclly/mt4-script-caller/releases)).

Please read carefully [README.md](https://github.com/micclly/mt4-script-caller/blob/master/README.md).
