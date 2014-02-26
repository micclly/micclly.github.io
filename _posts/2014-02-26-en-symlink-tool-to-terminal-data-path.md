---
layout: post
title: "(en) VBScript to create symlinks to MT4(build 600)/MT5 terminal data path"
description: ""
category: mt4
tags: [mt4,tools,english]
---
{% include JB/setup %}

I've written tiny VBScript to create symlinks to MT4 (build 600 and later) or MT5.

You can get from [GitHub](https://github.com/micclly/mt4-tools/blob/master/make-symlinks-to-terminal-data-path.vbs).

Both MetaTrader 4 (build 600 and later) and 5 stores application data (including experts, scripts)
to ``%APPDATA%\MetaQuotes\Terminal\<UNIQUEID>``.

It is so painful to open the directory if using multiple terminals.

This script creates symbolic links to all terminal data paths into current directory.
Symbolic link name is determined from origin.txt in terminal data path.

### Example

- MT4 Installation Directory
    - C:\Program Files\MetaTrader4
- Terminal Data Path
    - C:\Users\someone\AppData\Roaming\MetaQuotes\Terminal\AAAAABBBBBCCCCC
- Symbolic Link
    - Name: MetaTrader4
    - Link: C:\Users\someone\AppData\Roaming\MetaQuotes\Terminal\AAAAABBBBBCCCCC 
