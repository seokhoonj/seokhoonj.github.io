---
layout: post
title: openssl reinstall
category: Linux 
tags: [linux, openssl]
published: true
comments: true
---

openssl 설치 에러
----------------

R환경에서  openssl 설치 시 다음과 같은 에러가 발생하였다.

```console
Error: package or namespace load failed for ‘openssl’ in dyn.load(file, DLLpath = DLLpath, ...):
 공유된 객체 '/home/seokhoonj/R/x86_64-pc-linux-gnu-library/3.6/00LOCK-openssl/00new/openssl/libs/openssl.so'를 로드 할 수 없습니다:
  /home/seokhoonj/R/x86_64-pc-linux-gnu-library/3.6/00LOCK-openssl/00new/openssl/libs/openssl.so: undefined symbol: RSA_pkey_ctx_ctrl
에러: 로딩에 실패했습니다
실행이 정지되었습니다
ERROR: loading failed
* removing ‘/home/seokhoonj/R/x86_64-pc-linux-gnu-library/3.6/openssl’

다운로드한 소스 패키지들은 다음의 위치에 있습니다
	‘/tmp/RtmpelcZ0j/downloaded_packages’
경고메시지(들): 
In install.packages("openssl") :
  패키지 ‘openssl’의 설치가 0이 아닌 종료상태를 가졌습니다
```

이러한 문제를 해결하기 위해 다양한 방법을 강구해 보았으나 실패하였다.
다음은 openssl 패키지 설치 시 PKG_CFLAGS 정보이다.

```console
** using staged installation
Found pkg-config cflags and libs!
Using PKG_CFLAGS=-I/usr/local/include
Using PKG_LIBS=-L/usr/local/lib -l:libssl.so.1.1 -l:libcrypto.so.1.1
```

혹시 Sys.getenv()에 나오는 LD_LIBRARY_PATH의 문제는 아니었을까?

```console
strsplit(Sys.getenv()['LD_LIBRARY_PATH'], ":")

$LD_LIBRARY_PATH
[1] "/usr/lib/R/lib"
[2] "/usr/lib/x86_64-linux-gnu"
[3] "/usr/lib/jvm/java-11-openjdk-amd64/lib/server"
[4] "/usr/local/lib"
```
바꿔보았지만 문제는 해결되지 않았다. 결국 openssl을 다시 설치하기로 했다.

```console
$ cd /usr/src
$ sudo wget https://www.openssl.org/source/openssl-1.1.1c.tar.gz
$ tar -zxf openssl-1.1.1c.tar.gz
$ cd openssl-1.1.1c
$ sudo ./config
$ sudo make
$ sudo make test
$ sudo make install
```
/usr/local/lib 에 설치된 것을 알 수 있다.   
이제 libssl.so.1.1과 libcrypto.so.1.1 심볼릭 링크를 /usr/lib 에 만들자.
```console
$ sudo rm /usr/lib/libcrypto.so*
$ sudo rm /usr/lib/libssl.so*
$ sudo ln -s /usr/local/lib/libcrypto.so.1.1 /usr/lib/libcrypto.so
$ sudo ln -s /usr/local/lib/libssl.so.1.1 /usr/lib/libssl.so
$ sudo ln -s /usr/local/lib/libcrypto.so.1.1 /usr/lib/libcrypto.so.1.1
$ sudo ln -s /usr/local/lib/libssl.so.1.1 /usr/lib/libssl.so.1.1
```
실행파일도 바꿔보자.

```console
$ sudo mv /usr/bin/openssl /root/
$ sudo ln -s /usr/local/bin/openssl /usr/bin/openssl
```

하지만 여전히 R에서 openssl을 설치하면 여전히 오류가 발생한다!!!  
추가적으로 다음 경로의 실행파일도 바꿔 본다.

```console
$ sudo ln -s /usr/local/bin/openssl /usr/include/openssl 
$ sudo ln -s /usr/local/bin/openssl /usr/include/x86_64-linux-gnu/openssl
```

정상적으로 실행되는 것을 확인할 수 있다.
