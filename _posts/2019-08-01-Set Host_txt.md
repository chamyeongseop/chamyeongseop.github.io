---
layout: post
current: post
cover: assets/images/water.jpg
navigation: True
title: 호스트(host) 파일 설정
date: 2019-07-25 10:18:00
tags: Linux
class: post-template
subclass: 'post tag-fables'
logo: assets/images/ghost.png
author: akas
---
## hosts 파일 소개
- CentOS 7에서 DNS(Domain Name Server)보다 먼저 IP주소와 Hostname 또는 Domain 명을 Mapping하는 역할을 한다.
- 작은 네트워크에서는 DNS를 대신하도록 설정할 수 있다.

## hosts 설정
- Home 디렉토리에서 작업
{% highlight shell %}
sudo vi /etc/hosts
{% endhighlight %}
