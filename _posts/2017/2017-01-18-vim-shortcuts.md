---
layout: post
category : linux
tagline: "Think More"
tags : [linux, shell]
---
{% include JB/setup %}


## 插入模式
> 按「i」切换进入插入模式「insert mode」，按"i"进入插入模式后是从光标当前位置开始输入文件
> 按「a」进入插入模式后，是从目前光标所在位置的下一个位置开始输入文字
> 按「o」进入插入模式后，是插入新的一行，从行首开始输入文字

## 光标移动
> h向左移动，l向右移动，j移动到下一行，k移动到上一行
> Ctrl+b 向上翻页，Ctrl+f 向下翻页
> Shift+$移动到行尾，Shift+^移动到行首
> w移动到下一个单词，b移动到上一个单词
> gg移动到文档开始，G移动到文档结尾
> 跳转到第n行，ngg或者:n

## 删除文字
> x 删除光标后的一个字符
> nx 删除光标后的n个字符
> X 删除光标前的一个字符 
> nX 删除光标前的n个字符 
> dd 删除当前行
> ndd 从当前光标删除n行

## 复制粘贴
> yy 复制光标当前行
> p 粘贴

## 跳转
> gg 跳转至文档开始
> ngg 跳转至第n行
> G 跳转至文档末尾

## 多窗口
> :vnew 在当前vi窗口打开一个新的窗口
> Ctrl+w,h 光标切换到左边的窗口 
> Ctrl+w,b 光标切换到右边的窗口
> :close 关闭当前vi窗口

## 列出行号
> :set nu  列出行号

## 查找
> /关键字  全文查找关键字,如果第一次找的关键字不是您想要的，可以一直按「n」会往后寻找到您要的关键字为止。
> ?关键字  全文查找关键字,如果第一次找的关键字不是您想要的，可以一直按「n」会往前寻找到您要的关键字为止。

## 替换
> :s/vivian/sky/ 替换当前行第一个 vivian 为 sky
> :s/vivian/sky/g 替换当前行所有 vivian 为 sky
> :%s/vivian/sky/ 替换每一行的第一个 vivian 为 sky
>:%s/vivian/sky/g 替换每一行中所有 vivian 为 sky


待续更新。。。