---
layout: post
current: post
cover: assets/images/summit.jpg
navigation: True
title: /etc/hosts 설정
date: 2019-09-11 09:00:00
tags: Linux
class: post-template
fonts: Nanum Gothic
subclass: 'post tag-fables'
author: akas
---
# 호스트 파일 설정
## hosts 파일 소개
- /etc/hosts 파일에 리눅스 로컬네임서버 설정을 할 수 있다.
- 리눅스에서 hosts의 내용은 DNS(Domain Name Server)보다 먼저 탐색되어, 호스트명을 IP 주소로 풀어서 해석한다.
- 쉽게 풀어쓰면, 우리는 "NAVER" 또는 "DAUM" 검색 서비스를 이용할 때, 그들의 IP 주소를 입력하는 것이 아니라, 도메인명을 활용하여 서비스를 이용한다.

## 호스트(hosts) 설정
- /etc/hosts 파일을 편집한다.
- 각 서버들의 IP 주소 및 도메인명과 Alias 등의 정보를 넣어준다.

{% highlight bash %}
# hosts 설정 방법
[root@admin ~]# vi /etc/hosts
101.101.101.101 test1.도메인명.com test1 # IP주소 도메인 Alias(도메인의 별칭) 순으로 입력
101.101.101.102 test2.도메인명.com test2
101.101.101.103 test3.도메인명.com test3
101.101.101.104 test4.도메인명.com test4
{% endhighlight %}


{% highlight bash %}
/ 도메인명으로 PING TEST
[root@admin ~]# ping test1.도메인명.com
PING test1.도메인명.com (101.101.101.101) 4(8) bytes of data.

/ ALIAS로 PING TEST
[root@admin ~]# ping test1
PING test1 (101.101.101.101) 56(84) bytes of data.
{% endhighlight %}

## 호스트명 변경
### hostnamectl 명령어를 활용하는 방법
- Network hostname을 test.domainName.com으로 설정
- Home 디렉토리에서 작업을 수행한다.

{% highlight bash %}
[root@admin ~]# sudo hostnamectl set-hostname test.
{% endhighlight %}
