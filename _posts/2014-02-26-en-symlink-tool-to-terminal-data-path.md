---
layout: post
title: "(en) VBScript to create symlinks to MT4(build 600)/MT5 data folder"
description: ""
category: mt4
tags: [mt4,tools,english]
---
{% include JB/setup %}

I've written tiny VBScript to create symbolic links to the data folder of MT4 (build 600 and later) and MT5.
This VBScript only can be run on Windows Vista and later.

You can get from [GitHub](https://github.com/micclly/mt4-tools/blob/master/make-symlinks-to-terminal-data-path.vbs).

Both MetaTrader 4 (build 600 and later) and 5 stores application data (including experts, indicators and scripts)
to ``%APPDATA%\MetaQuotes\Terminal\<UNIQUEID>``.

It is so painful to open the data folder if using multiple terminals.

This script creates symbolic links to all data folders into current directory.
Symbolic link name is determined from origin.txt in data folders.

### Example

- MT4 Installation Directory
    - C:\Program Files\MetaTrader4
- Data Folder
    - C:\Users\someone\AppData\Roaming\MetaQuotes\Terminal\AAAAABBBBBCCCCC
- Symbolic Link
    - Name: MetaTrader4
    - Link: C:\Users\someone\AppData\Roaming\MetaQuotes\Terminal\AAAAABBBBBCCCCC 
