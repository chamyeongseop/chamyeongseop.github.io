---
layout: post
current: post
cover: assets/images/summit.jpg
navigation: True
title: Stack 과 Queue 정리
date: 2019-09-11 09:00:00
tags: DS
class: post-template
fonts: Nanum Gothic
subclass: 'post tag-fables'
author: akas
published: true
---
# Stack
- 한 쪽 끝에서만 자료를 넣고 뺄 수 있는 자료 구조.
- 마지막으로 넣은 것이 가장 먼저 나오기 때문에 Last In First Out (LIFO) 라고 한다.
- "스택"에서 데이터가 들어가고 나가는 곳을 "한 지점"에 고정을 시켜놓고, 명령어를 수행한다.


## Stack 명령어 정리
- push : 스택에 자료를 넣는 연산
- pop : 스택에 자료를 빼는 연산
- top : 스택의 가장 위에 있는 자료를 보는 연산
- empty : 스택이 비어있는지 아닌지를 알아보는 연산
- size : 스택에 저장되어 있는 자료의 개수를 알아보는 연산

## 대표 문제 유형
- 괄호 문제(짝 맞추기 문제)
- 스택 수열
- 단어 뒤집기
- 에디터 문제


# Queue
- 한 쪽 끝에서만 자료를 넣고, 다른 한 쪽 끝에서만 뺄 수 있는 자료 구조
- 먼저 넣은 것이 가장 먼저 나오기 때문에 First In First Out(FIFO) 라고 한다.
- 삭제 연산은 Begin 쪽에, 삽입 연산은 End 쪽에서 이루어진다.
- C++의 경우에는 STL의 queue를 사용하고, Java의 경우에는 java.util.Queue를 사용하는 것이 좋다.

## Queue 명령어 정리
- push : 큐에 자료를 넣는 연산
- pop : 큐에서 자료를 빼는 연산
- front : 큐의 가장 앞에 있는 자료를 보는 연산
- back : 큐의 가장 뒤에 있는 자료를 보는 연산
- empty : 큐가 비어있는지 아닌지를 알아보는 연산
- size : 큐에 저장되어있는 자료의 개수를 알아보는 연산

## 대표 문제 유형
- 조세퍼스 문제

# Deque (덱)
- 양 끝에서만 자료를 넣고 양 끝에서 뺄 수 있는 자료구조
- Double-ended queue의 약자

## Deque 명령어 정리
- push_front : 큐에 자료를 넣는 연산
- pop : 큐에서 자료를 넣는 연산
- front : 큐의 가장 앞에 있는 자료를 보는 연산
- back : 큐의 가장 뒤에 있는 자료를 보는 연산
- empty : 큐가 비어있는지 아닌지를 알아보는 연산
- size : 큐에 저장되어 있는 자료의 개수를 알아보는 연산
