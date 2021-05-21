---
layout: post
title: Markdown 基礎語法
tags:
    - "markdown"
toc: true
---

Markdown 的格式、標題、列表、標記重點及其他基本功能。
<!-- more -->
### 段落和換行

一個以上的空行則會切分出不同的段落（只要顯示上看起來像是空行，便會被視為空行）。  
Markdown 允許段落內的強迫斷行，只要在行尾加上兩個以上的空白，然後按 Enter。

### 標題

行首的 `#` 數量決定標題的階數。可在行尾加上 `#`，且行尾的 `#`數量不必和行首相同。（此區塊標題為 h3，1～6 由大到小）

<div class="no_toc_section">
<h1>這是 h1</h1>
<h2>這是 h2</h2>
<h6>這是 h6</h6>
</div>

```
# 這是 h1
## 這是 h2 ##
###### 這是 h6 ###
```

### 區塊引言

> 在文字的最前面加上 >，
> 就能建立一個區塊引言

> 可以整個段落
只加一個 >

> 也可以有
> > 不同階層的引言
> 
> （根據層數加上不同數量的 >）

> 可以使用其他 Markdown 語法，如
> 1. 第一項
> 2. 第二項
> 
> ```py
> print("hello, world!")
> ```

```
> 在文字的最前面加上 >，
> 就能建立一個區塊引言

> 可以整個段落
只加一個 >

> 也可以有
> > 不同階層的引言
> 
> （根據層數加上不同數量的 >）


> 可以使用其他 Markdown 語法，如
> 1. 第一項
> 2. 第二項
>
> ```py
> print("hello, world!")
> ```
```

### 列表

Markdown 支援有序與無序列表。  
無序列表使用星號 `*`、加號 `+` 或是減號 `-` 作為列表標記：

- red
- blue
- green

```
- red
- blue
- green
```

有序列表則使用數字加一個英文句點，即使列表編號不按照順序，依然能得到正確的結果（還是建議按照順序編寫）：

6. red
1. blue
6. green

```
6. red
1. blue
6. green
```

列表可使用縮排，至多三個空白。列表符號與文字間必須有至少一個空格或 tab。  
若列表用一個空行分隔，會顯示為另一個獨立的列表：

- one
- two

- three

```
- one
- two

- three
```

列表項目可以包含多個段落，每個項目下的段落都必須縮排 4 個空白或是一個 tab（為了美觀，建議每行都進行縮排）：

1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.

```
1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.
```

若需要在列表放入引言或程式碼區塊，則必須加入縮排：

* 有程式碼區塊在引言內的列表：

  > ```py
  > print("hello, world!")
  > ```

```
* 有程式碼區塊在引言內的列表：

  > ```py
  > print("hello, world!")
  > ```
```

若要避免一般的英文句點變成列表，只要在前面加上跳脫字元 `\` 即可：

1986\. What a great season.
```
1986\. What a great season.
```

### 程式碼區塊

#### 行內程式碼

用反引號 <code>`</code> 將文字包起來即為行內程式碼：  
`-` 為列表符號

```
`-` 為列表符號
```

#### 區塊程式碼

用三個反引號 <code>```</code> 的單行圍起來，在第一行後面輸入語言可以使用語法高亮：

```py
n = 5
for i in range(n):
  print("*" * i)
```

### 分隔線

使用三個或以上的星號、減號、底線可建立一個分隔線 ，也可以在中間插入空白： 

***

以下都可達成一樣的效果：

```
* * *
***
_ ___
---------
```

### 連結

#### 行內樣式

[行內樣式連結](https://www.google.com)

[加上標題的行內樣式連結](https://www.google.com "Google 首頁")

[也可以使用相對連結](../tag/markdown.html)

```
[行內樣式連結](https://www.google.com)

[加上標題的行內樣式連結](https://www.google.com "Google 首頁")

[也可以使用相對連結](../tag/markdown.html)
```

#### 引用樣式

[這是一個引用樣式的連結][任意不區分大小寫的文字]

引用連結可以在其他文字後面

[也可以用數字宣告][1]

[或者用連結文字本身]

[任意不區分大小寫的文字]: https://www.google.com
[1]: https://www.google.com
[或者用連結文字本身]: https://www.google.com

```
[這是一個引用樣式的連結][任意不區分大小寫的文字]

引用連結可以在其他文字後面

[也可以用數字宣告][1]

[或者用連結文字本身]

[任意不區分大小寫的文字]: https://www.google.com
[1]: https://www.google.com
[或者用連結文字本身]: https://www.google.com
```

### 圖片

用法語連結相同，但需要在前面加上 `!`，中括號的內容會在圖片失效時顯示：
![圖片失效才會顯示](https://upload.wikimedia.org/wikipedia/commons/4/48/Markdown-mark.svg "Markdown logo")

```
![圖片失效才會顯示](https://upload.wikimedia.org/wikipedia/commons/4/48/Markdown-mark.svg "Markdown logo")
```