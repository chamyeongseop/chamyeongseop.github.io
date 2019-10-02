---
layout: post
current: post
cover: assets/images/sky.jpg
navigation: True
title: JAVA의 length, length(), size 비교
date: 2019-09-11 09:00:00
tags: JAVA
class: post-template
fonts: Nanum Gothic
subclass: 'post tag-fables'
author: akas
published: true
---
# JAVA의 LENGTH, LENGTH(), SIZE 사용 및 비교


## length
- arrays (int[], double[], String[]) : 배열의 길이를 알려 할때 사용한다.
- 메소드가 아니므로, Object로 사용하지 않는다. 따라서 오직 배열에서만 사용할 수 있다.

## length()
- String related Object (String, StringBuilder etc) : 이것은 문자열의 길이를 알고자 할때 사용된다.
- 스트링은 배열이 아니므로, .length를 사용할 수 없으며, 컬렉션 또한 아니기 때문에, .size() 도 사용할 수 없다. 이를 위해 length()가 설계되었다.

## size()
- Collection Object (ArrayList, Set etc) : 컬렉션 타입의 길이를 확인할때 사용된다.
- 메소드이므로, Collection에 사용될 수 있다.


# 지역변수 및 전역변수 신중하게 사용하기.
- 지역 변수와 전역 변수를 구분하는 기준은, 변수를 블록 내(if, for 구문)에서만 사용가능하느냐 아니면 전체에서 사용 가능하느냐의 차이.
- 전역 변수는 블록 내에서 모두 사용가능하지만, 지역 변수로 활용이 되고 있는 부분이 블록 밖에서는 Compile 오류가 발생한다.
- 전역 변수는 함수 밖에서 선언하며, 어디에서든지 접근 가능한 변수.
