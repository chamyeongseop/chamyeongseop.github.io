---
layout: post
current: post
cover: assets/images/speeches.jpg
navigation: True
title: JAVA 바이트코드(bytecode) 정리
date: 2019-10-30 09:00:00
tags: JAVA
class: post-template
fonts: Nanum Gothic
subclass: 'post tag-fables'
author: akas
published: true
---
해당 포스트는 "이상현"님의 자바 바이트코드 소개를 참고하여, 작성되었습니다.
# JAVA 바이트 코드 소개


## 컴파일러
- 자바 바이트 코드는 JVM(Java Virtual Machine)이 실행하는 명령어 집합입니다. 컴파일을 하면 생성되는 .class 파일이 바이트 코드를 담고 있습니다.
- 컴파일을 통해 생성 된 파이트 코드 파일은 OS나 개발환경에 관계없이 같은 명령어 집합을 사용하며, 이것이 자바의 크로스 플랫폼 동작을 가능하게 해줍니다.

![JVM 구조](/assets/images/JVM3.JPG "바이트코드 실행 과정")

- 바이트코드 실행 과정에서 두 종류의 컴파일러가 있습니다.
  - 첫번째 컴파일러는 자바 코드를 자바 클래스 파일로 만들어주는 컴파일러입니다.
    - javac로 표기된 부분으로써, JDK(Java Development Kit)에 포함된 기본 컴파일러입니다.
    - 해당 작업 이후에, JRE(Java Runtime Environment)에서 더 나은 최적화를 하기 위해, 이후에 loop unrolling, algebraic simplicatin, strength reduction 같은 기본적인 최적화도 하지 않습니다.
    - 두번째 컴파일러는 JIT(Just In Time) 컴파일러로써, JVM은 동적으로 바이트코드를 읽으며 인터프리팅을 하는데, 이 단계에서 JIT 컴파일러는 자바 애플리케이션의 성능향상을 위해, 동적 컴파일을 통해 머신 코드(Machine Code)로 컴파일 가능한 코드들을 한 번 더 컴파일합니다.
      - 미리 컴파일 하지 않고, 실행 중에 동적으로 컴파일 작업을 수행합니다.
