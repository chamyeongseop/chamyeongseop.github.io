---
layout: post
current: post
cover: assets/images/writing.jpg
navigation: True
title: JAVA Memory 간단 정리
date: 2019-10-31 09:00:00
tags: JAVA
class: post-template
fonts: Nanum Gothic
subclass: 'post tag-fables'
author: akas
published: true
---

# JAVA Memory
- JAVA 8을 기준으로 JVM 메모리 영역에 변화(Metaspace 등장)가 있었으며, JAVA Memory의 구성요소들을 살펴보자.
- JAVA Memory 영역은 Runtime Data Area라고 불리우며, 여러 영역으로 나누어져 있다.

## Method Area
- JVM에서 읽은 클래스와 인터페이스 정보가 저장되는 영역으로, 클래스 생성자 및 바이트 코드가 저장된다.
- Class의 인스턴스가 생성된 후, 메소드가 실행되는 순간, 클래스의 정보가 Method Area에 저장된다.
- Method Area는 모든 Thread에 의해 공유되는 영역으로써, JVM이 시작될 때 생성된다.

### Method Area - Runtime Constant Pool
- Method Area는 내부에 Runtime Constant Pool 영역을 가지고 있으며, 해당 영역에는 클래스 및 인터페이스의 메소드, 필드, 문자열 상수 등의 레퍼런스가 저장되며, 이들의 물리적인 메모리 위치를 참조할 경우에 사용된다.

## Heap
- new 연산자 등으로 생성 된 객체(인스턴스)와 배열 등이 저장되는 영역이다.
- Heap 영역에 저장된 객체(인스턴스)나 배열은 다른 객체에서 참조될 수 있다.
- GC(Garbage Collection)이 발생하는 영역이며, 참조가 없는 객체들은 GC과정을 통해 메모리에서 제거된다.
- Heap 영역 또한 내부적으로 여러 영역으로 구성되어 있으며, 이는 객체의 lifecycle과 GC와 연관되어 있다.(튜닝 옵션: -Xms, -Xmx)

## JVM Language Stacks
- 메소드 호출 시 수행 중인 메소드 데이터(지역변수, 지역객체 레퍼런스, 메소드 파라미터, 메소드 리턴값 등)를 저장하기 위한 영역이다.
- Stack 영역은 Thread 별로 각각 독립적으로 생성된다.
- Stack 영역에는 메소드 진입시마다 메소드 데이터를 포함하는 Stack Frame이 생성되어 push되며, 메소드 생성이 완료되면, Stack Frame은 pop되어 사라진다.

## PC Registers
- 각 Thread 마다 할당되는 영역으로, Thread가 시작될 때 생성된다.
- PC Registers 영역에는 Thrad가 실행할 JVM 명령(바이트 코드 명령)의 주소를 저장하게 된다.

## Native Method Area는
- JAVA 외의 언어로 작성된 코드(Native code, JNI로 실해오디는 코드)를 위한 Stack 영영으로, 각 언어에 맞는 Stack이 생성된다.

![JVM 메모리 구조](/assets/images/JVM_memory.jpg "JVM Memory 구조")


# Heap 영역 자세히 살펴보기
- Heap 영역은 new 연산자 등으로 생성 된 객체(인스턴스)와 배열 등을 저장하는 영역으로, GC가 발생한다.
- GC는 한정적인 메모리 자원을 효율적으로 사용하기 위해, 더 이상 불필요한 리소스들을 메모리에서 제거하는 작업을 의미한다.
- Heap 영역은 Eden, Suvivorm Old, Permanent 영역으로 구성되어 있다.

## Eden 영역(Young 영역)
- 새로 생성 된 대부분의 객체가 처음 위치하는 영역이다.
- Eden 영역에서는 정기적으로 GC가 발생하며, 이후에 살아남은 객체들은 Suvivor 1 또는 Survivor 2 영역 중 하나의 영역으로 이동하여, 저장된다.

## Survivor 1, Survivor 2 영역(Young 영역)
- Survivor 1, Survivor 2 중 하나의 영역이 꽉 차게되면, 그 중 살아남은 객체들은 비워 진 Survivor 영역으로 이동한다. 이동 시, 참조가 없는 객체들은 메모리에서 정리된다.
- 위와 같은 매커니즘으로 인해, Survivor 1 또는 Survivor 2는 항상 비워진 상태가 되며, Survovir 영역 중 하나의 영역이 완전히 비워지지 않았다면, 문제가 있다.

### Minor GC
- Eden 영역 또는 Survivor 영역 등, Young 영역에서 발생하는 GC를 minor GC라고 한다.

## Old 영역
- Survivor 1, Survivor 2 영역을 왔다갔다 하는 과정에서 끝까지 살아남은 객체만이 Old 영역으로 이동하게 된다.
- 보통 Old 영역은 Young 영역보다 크게 할당하며, 이러한 이유로 Old 영역의 GC는 Young 영역보다 적게 발생한다.

### Major GC
- Old 영역, Permanent 영역에서 발생하는 GC를 Major GC(Full GC)라고 한다.

## Permanent 영역
- 클래스 로더에 의해 로드 된 클래스들이 저장되는 공간이다. JAVA 8에서는 Permanent 영역이 조금 더 다듬어져서 Metaspace라는 영역으로 교체되었다.
