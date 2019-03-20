---
layout: post
title: R 패키지 구성하기 
category: R
tags: [R, package]
published: false 
comments: false 
---

R 패키지 구성하기 
-------------

``` r
library(devtools)
library(roxygen2)

create_package("ecos")
```

```bash
vim DESCRIPTION
```

```R
cd ~/ecos
library(devtools)
check_win_release()
```
