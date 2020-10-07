---
title: Spring security設定
date: "2020-10-07T11:12:03.284Z"
description: "記錄spring security的設定，搭配JWT作為驗證手段"
---

### 一、繼承WebSecurityConfigurerAdapter的securuty 設定

```
public class SecurityConfig extends WebSecurityConfigurerAdapter {
  @Override
  protected void configure(HttpSecurity httpSecurity) throws Exception {
    
  }
}
```

最基本的得創建一個類別，繼承WebSecurityConfigurerAdapter，並且override其中的configure設定，
如此可以客製化自己的serurity配置。