---
layout: post
title: "rake aborted!"
date: 2015-07-18 15:10:59 +0800
comments: true
categories: 
---
今天心血來潮去 `_config.yml` 裡面把一些 3rd party 的功能開來用，

沒想到 `rake generate` 時出現 `rake aborted!`，

看一下敘述直覺是前幾天 `homebrew` 更新 `openssl` 造成的，

搜尋並試了一些方法後終於用下面這個方法解掉這個問題，

```
$ rvm get stable
$ rvm reinstall ruby-1.9.3-p0
$ rvm gemset pristine
$ rvm gemset empty mygemset
$ gem install bundler
$ bundle install
```

***

### 參考資料
- [Ruby Bundle Symbol not found: _SSLv2_client_method (LoadError)](http://stackoverflow.com/questions/25492787/ruby-bundle-symbol-not-found-sslv2-client-method-loaderror)
