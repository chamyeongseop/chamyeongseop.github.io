---
layout: post
current: post
cover: assets/images/sky.jpg
navigation: True
title: JAVA의 Iterator와 enumerate 정리
date: 2019-10-02 09:00:00
tags: JAVA
class: post-template
fonts: Nanum Gothic
subclass: 'post tag-fables'
author: akas
published: true
---

# Synchronous(동기) VS Asynchronous(비동기)
- 동기(Synchronous)sms 어떤 작업이 실행되고, 그 작업이 완료될 때까지 다른 작업을 수행할 수가 없다. 이전의 작업이 완료되어야, 다음의 작업을 수행할 수 있다.
- 하지만 비동기(Asynchronous)는 하나의 작업 수행이 완료되지 않아도, 기다리지 않고 다음 작업을 실행한다. 다만 이전부터 수행하고 있던 작업들이 끝나면, 신호를 알려준다.


## Asynchronous programming (비동기 프로그래밍)과 AsyncioAsyncio
- AsyncioAsyncio는 async/await 문법을 사용해 동시성(Concurrent) 코드를 사용할 수 있게 해주는 라이브러리이다.
- 대표적인 장점으로는 시간이 오래 걸리는 작업을 실행했을 때, 결과를 기다리지 않고, 다음 작업을 실행할 수 있다.

# Java Iterator
- Iterator는 반복자라는 뜻으로, Iterator 인터페이스는 자료를 얻어내는데 사용된다.
- iterator() 메소드는 컬렉션(Collection) 자료형이라면 관계없이 사용가능하다.

- For문을 통해 충분히 자료들을 꺼내올 수 있는데, 굳이 Iterator를 사용하는 이유가 무엇일까?
- Ans) ArrayList에 담긴 데이터를 Set으로 옮겼다면, 일반적으로 출력문까지 전면 수정이 필요하지만, Iterator는 데이터를 빼오는 방식을 표준화하는데 목적이 있기 때문에, 코드의 재활용이 가능하다(다형성)

## Iterator 인터페이스에서 사용되는 메소드
### hasNext()
- 뒤에 남은 데이터가 있다면 True, 없다면 False를 반환한다. while 루프를 통한 제어처리시 사용한다.

### next()
- 자료구조의 다음 데이터를 반환하여, 다음 객체의 레퍼런스를 얻는다.

### remove()
- 현재 조회하는 객체의 레퍼런스를 삭제한다.



# Enumeration
- Enumeration은 Iterator에서 remove() 메소드만 빠지고, 이름만 다를 뿐 사용법은 같다. (Iterator의 구버전)

## Enumeration의 메소드
### hasMoreElements()
- Iterator의 .hasNext()와 같은 기능이다.

### nextElement()
- Iterator의 next()와 같은 기능이다.

# ListIterator
- ListIterator는 Iterator를 상속받아서 기능을 추가한 것이다.
- 컬렉션의 요소에 접근할 때, Iterator는 단방향으로만 이동할 수 있지만, ListIterator는 양방향으로 이동이 가능하다는 장점이 있다.
- ArrayList나 LinkedList처럼 List 인터페이스를 구현한 컬렉션 클래스에서만 사용이 가능하다.
