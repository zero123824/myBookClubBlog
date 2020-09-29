---
title: Gatsby操作步驟紀錄
date: "2020-09-29T13:53:03.284Z"
description: "太久沒有用gatsby來操作blog，記錄一下如何操作gatsby，方便之後寫文章部屬到github page。"
---

# 一、建立MD檔

在/content/blog 目錄底下建立一個文章資料夾，裡面有md檔。其中可以包含assets放靜態圖片資源。

# 二、編譯

輸入```npm run build```指令，markdown檔案將被編譯成html檔案和其他靜態資源。

# 三、測試

輸入```npm run serve```指令，在localhost端起server預覽寫出的東西正不正確。

# 四、部屬

輸入```npm run deploy```指令，改變的東西將被部屬到gh-pages分支，github page上就可以看到。