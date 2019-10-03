---
title: Java Reactor介紹
date: "2019-10-03T15:31:03.284Z"
description: "介紹Java的reative programming的實作庫:Reactor"
---

## 一、Java Reactor基本method介紹:

reactor是java library對於 reactive programming的實現，關注在資料流的傳遞與變化。

```
比如求值一个简单的表达式 c=a+b，当 a 或者 b 的值发生变化时，传统的编程范式需要对 a+b 进行重新计算来得到 c 的值。如果使用反应式编程，当 a 或者 b 的值发生变化时，c 的值会自动更新。
```

Java裡幾個有名的reactive library: RxJava/RxJava2/Reactor

Spring5的Spring webflux是基於reactor實現web應用的框架。

## 二、Return值的mono & flux

flux是一種訂閱者模式，表示的是包含 0 到 N 个元素的异步序列，可以包含三种不同类型的消息通知：正常的包含元素的消息、序列结束的消息和序列出错的消息。当消息通知产生时，订阅者中对应的方法 onNext(), onComplete()和 onError()会被调用。

mono也是訂閱者模式，表示的是包含 0 或者 1 个元素的异步序列，flux與mono之間可以進行轉換，像是List<Object>與Object之間的關係。

## 三、建立Flux

靜態生成:從一個固定的集合中產生flux

```java
 public static void main(String[] args) {
        Flux.just("Hello", "World").subscribe(System.out::println);
        Flux.fromArray(new Integer[] {1, 2, 3}).subscribe(System.out::println);
        Flux.empty().subscribe(System.out::println);
        Flux.range(1, 10).subscribe(System.out::println);
 }
```

動態生成: generate()方法





參考資料:

[從響應式編程談到"好萊塢"](https://www.twblogs.net/a/5d733708bd9eee541c3415d5)

[異步編程與多線程編程的聯系和區別](https://www.itread01.com/content/1553169850.html)

[Reactor 3 之选择合适的操作符——响应式Spring的道法术器](https://blog.51cto.com/liukang/2094073)

[响应式Spring的道法术器（Spring WebFlux 快速上手 + 全面介绍）](https://blog.51cto.com/liukang/2090163)