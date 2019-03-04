---
layout: post
title: zip으로 분할 압축하기
category: Ubuntu
tags: [Ubuntu, zip]
published: true
comments: true
---

zip으로 분할 압축하기
----------------

협업을 하다보면 파일 용량의 제한 때문에 분할 압축을 해서 전송해야 할 경우가 생긴다.
만약 res 라는 폴더에 다양한 결과파일이 있고 이를 한꺼번에 res.zip이라는 파일로,
각각 10mb 단위로 분할 압축하고자 하면,

``` console
$ zip -s 10M res.zip ./res/*
```

이 과정을 거치면 용량의 크기에 따라서 다르지만,
res.z01 / res.z02 / res.z03 / ... / res.zip 으로 압축된 파일이 구성된다.

압축을 해제하는 방법은 다음과 같다.

```console
$ mv res.z* ~                         # 압축파일을 사용자 폴더로,
$ zip -s 0 res.zip --out res-full.zip # res-full.zip 으로 통합
$ unzip res-full.zip                  # res-full.zip 파일을 압축 해제
```

