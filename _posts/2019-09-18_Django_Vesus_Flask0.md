---
layout: post
current: post
cover: assets/images/sky.jpg
navigation: True
title: Java Map 정리 (Hashmap, Treemap, LinkedHashMap)
date: 2019-11-07 09:00:00
tags: JAVA
class: post-template
fonts: Nanum Gothic
subclass: 'post tag-fables'
author: akas
published: false
---

# HashMap
- 내부적으로 Entry<K,V>[] Entry의 배열로 구성되어 있다.
- 해당 배열에 index 값은 내부의 해쉬 함수를 통해 계산된다.
  - String : sun.misc.Hasing.stringHash32 함수를 사용
  - Object : 내부 Hashcode 함수와 비트연산을 사용
'''java
1 Map<String, String> map = Maps.newHashMap();
2 map.put("c", "1");
3 map.put("a", "1");
4 map.put("b", "1");
5 map.put("k", "1");
6 for (String s : map.keySet()) {
7     System.out.println(s);
8 }
9 // b, c, a, k 출력

'''

# TreeMap
- 내부적으로 Redblack tree로 저장된다.
- 키 값에 대한 Comparator 구현으로 정렬 순서를 바꿀 수 있다.
'''java
1 Map<String, String> map = Maps.newTreeMap();
2 map.put("c", "1");
3 map.put("a", "1");
4 map.put("b", "1");
5 map.put("k", "1");
6 for (String s : map.keySet()) {
7     System.out.println(s);
8 }
9 // a, b, c, k 출력
'''

# LinkedHashMap
- 링크드 리스트로 저장된다.
- 키 값은 입력 순서대로 출력되어 나온다.
'''java
1 Map<String, String> map = Maps.newLinkedHashMap();
2 map.put("c", "1");
3 map.put("a", "1");
4 map.put("b", "1");
5 map.put("k", "1");
6 for (String s : map.keySet()) {
7     System.out.println(s);
8 }
9 // c, a, b, k 출력
'''

## 정리
- 특별한 이유가 없다면 검색성능이 좋은 O(1) HashMap을 사용하자.
- 키 값이 일정한 수준대로 iterate 하려고 한다면 TreeMap을 사용하자. 하지만 랜덤 접근에 대해서는 O(logn) 성능을 지니므로, 많은 데이터를 넣을 경우에는 좋지 않은 성능이 나올 수 있다.
- 입력 순서가 의미가 있다면 LinkedHashMap을 사용하자. 랜덤 접근에 대해 O(n) 성능을 지니므로 많은 데이터를 입력할 경우에는 사용하지 않는 것이 좋다.
