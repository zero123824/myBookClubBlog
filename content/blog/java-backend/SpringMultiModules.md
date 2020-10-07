---
title: Spring專案拆分多模組簡介
date: "2020-09-30T11:50:03.284Z"
description: "簡介Spring專案拆分多模組的方法步驟,以及注意事項"
---

### 一、intellij新增專案
使用intellij新建一個spring boot專案，如一般設定。
完成後可以先值節application的main方法，確認新建成功。

### 二、新增模組
在專案下右鍵有個New -> Module，裡面可以決定module的名稱，finish後，child module會掛在parent module底下。

### 三、搬移parent模組的內容
在parent這層是沒有src之類的java file，只有pom file定義了個模組間的關係。 
而要將Package中自動產生的名稱改為與parent一樣，因為web的應用程式類別的@SpringBootApplication的scanBasePacages屬性會設定為"parent的package name的package name"，spring boot會按照這個設定掃描物件為bean。

### 四、檢視module pom.xml檔
```
    <modules>
        <module>entity</module>
    </modules>
```
parent module的pom檔案裡面會新增modules的tag，裡面有相依的child module
而在child module的pom.xml裡
```
    <parent>
        <artifactId>multimodule</artifactId>
        <groupId>idv.jaime</groupId>
        <version>0.0.1-SNAPSHOT</version>
    </parent>
```
有parent module的資訊

### 五、設定repository的resouce
當想要把與資料庫相關的orm，包括repository和domain vo拆開時，再次啟動applcation會發現找不到datasource的url設定，而明明已經在主要專案的application.properties中設定。
這是因為沒有正確讀取到配置文件，需要在parent modules的pom檔中設定:
```
<build>
  <resouces>
    <directory>
  
    </directory>
  </resouces>
</build>
```
這樣的配置



