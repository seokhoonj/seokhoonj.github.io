---
layout: post
title: Disable ubuntu touchscreen
category: Ubuntu
tags: [Ubuntu, touchscreen]
published: true
comments: true
---

우분투 터치스크린 오프하기
----------------
18년 5월 미국에서 구입한 Dell xps 9370에 Ubuntu 18.04와 Windows 10 Pro를 설치하여,  
큰 문제 없이 사용하고 있었다. 그런데 최근 들어 갑자기 커서가 엣지쪽으로 이동하면서 
마구잡이로 클릭을 되는 이상한 현상이 발생하였다.

쭉 델 제품만 사용하면서 모니터의 디스플레이나 배터리 문제를 경험한 경우는 있었지만,
이런 현상은 첨 겪어 보는 일이어서 배터리 방전, 터치패드 관련 드라이버 재설치 등 다양한 
시도를 해보았지만 결과는 실패.

결국 델 서비스센터에 연락을 하였고, 만약 수리를 하게 된다면 소유권 이전 문제 (미국에서 구입) 등  
절차적으로 해결해야할 문제가 있어 시간이 다소 소요될 것이라는 대답을 듣게 되었다. 
하지만 분석 컨설팅 기간 동안 노트북이 없다면 엄청난 불편을 감수해야하기 때문에,  
일단 터치스크린이 작동하지 못하도록 한 후 사용하기로 결정했다.

우분투 터치스크린을 오프하는 방법은 다음과 같다.

``` console
$ cd /usr/share/X11/xorg.conf.d
$ sudo vim 40-libinput.conf
```

```vim
Section "InputClass"
        Identifier "libinput touchscreen catchall"
        MatchIsTouchscreen "on"
        MatchDevicePath "/dev/input/event*"
        #Driver "libinput"
        __Option "Ignore" "on"__
EndSection
```

``` console
$ sudo reboot
```
