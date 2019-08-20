---
layout: post
current: post
cover: assets/images/summit.jpg
navigation: True
title: Array와 LinkedList 정의 및 비교
date: 2019-08-14 10:18:00
tags: DS
class: post-template
subclass: 'post tag-fables'
logo: assets/images/profile2.png
author: akas
published: False
---
## Array
Array(배열)은 논리적 저장 순서와 물리적 저장 순서가 일치한다. 따라서 인덱스(index)를 활용하여, 특정 원소(element)로 접근할 수 있다. 따라서 찾고자 하는 원소의 인덱스 값을 알고 있으면 Big-O(1)에 해당 원소로 접근할 수 있다. 즉, Random Access가 가능하다는 장점이 존재한다.

하지만 삭제(Delete) 또는 삽입(Insert)의 작업을 수행할 때, 특정 원소에 접근하여 작업을 완료한 뒤(O(1)), 한 가지 작업을 추가적으로 수행해야한다. 만약 배열의 원소 중 어느 원소를 삭제했다고 했을 때, 배열의 연속적인 특징이 깨지게 된다. 즉 빈 공간이 생기는 것이다. 따라서 삭제한 원소보다 큰 인덱스를 갖는 원소들을 왼쪽 또는 오른쪽으로 이동(shift)해야 하는 비용(cost)이 발생하고 이 경우의 시간 복잡도는 O(n)가 된다. 그렇기 때문에 Array에서 삭제 작업으로 발생되는 time complexity의 worst case 는 O(n)이 된다.

삽입의 경우도 마찬가지이다. 만약 첫번째 자리에 새로운 원소를 추가하고자 할 때, 나머지 원소들의 인덱스를 1 만큼 오른쪽으로 shift 작업이 필요하므로, 이 경우도 O(n)의 시간이 걸린다.


## ArrayList Versus LinkedList
ArrayList는 데이터들이 순서대로 쭉 늘어선 배열의 형식을 취하고 있다. ArrayList는 사이즈가 고정되어 있기 때문에 사입 시 사이즈를 늘려주는 연산이 추가되어야 하고, 삭제 시에는 순차적인 인덱스 구조로 인해, 삭제 된 빈 인덱스를 채워야하는 연산이 추가되어야 한다. 따라서, 삽입 및 삭제가 빈번하게 발생하는 프로레스의 경우 시스템의 성능 저하를 일으키는 원인이 된다. 또한 자료들이 지속적으로 삭제되는 과정에서 ArrayList에서는 그 공간만큼 낭비되는 메모리가 많아지게 된다.


LinkedList는 각각의 원소(element)들이 서로 자료의 주소 값으로 연결되어 있는 구조이다. 따라서 몇 개의 참조자만 다른 값으로 변경한다면, 삭제와 삽입을 O(1)에 해결 할 수 있다. LinkedLisst는 ArrayList에서 발생하는 문제를 연결 형태(Linked)로 해결하여, ArrayList에서 뒤로 밀거나 채우는 작업 없이 단지 주소만 서로 연결시켜 준다면, 추가 및 삭제가 ArrayList보다 빠르고 용이하다. 따라서 삽입 및 삭제가 빈번하게 발생하는 프로세스의 경우에는 LinkedList를 사용하여, 시스템을 구현하는 것이 바람직하다.

LinkedList도 단점이 존재한다. ArrayList는 무작위 접근(Random Access)가 가능하지만, LinkedList에서는 순차접근(Sequential Access)만이 가능하다. 특히 LinkedList는 단방향성을 갖고 있기 때문에 인덱스를 이용하여, 자료를 검색하는 어플리케이션에는 적합하지가 않다.  

사실 순차 접근도 참조의 지역성(locality of reference: 한번 참조한 데이터는 다시 참조될 가능성이 높고 참조된 데이터 주변의 데이터 역시 같이 참조될 가능성이 높다는 이론입니다.) 때문에 LinkedList 보다는 ArrayList가 훨씬 빠릅니다. n개의 자료를 저장할 때, ArrayList는 자료들을 하나의 연속적인 묶음으로 묶어 자료를 저장하는 반면, LinkedList는 자료들을 저장 공간에 불연속적인 단위로 저장하게 됩니다. 그렇기 때문에 LinkedList는 메모리 이곳저곳에 산재해 저장되어 있는 노드들을 접근하는데 ArrayList보다는 긴 지연 시간이 소모됩니다. LinkedList의 또 다른 단점은 참조자를 위해 추가적인 메모리를 할당해야 하는 점입니다. 자료들의 크기가 작은 리스트의 경우 참조자를 위한 추가적인 메모리할당은 비실용적일 수 있습니다.

## 정리
<h2 id="table">Table</h2>

<table>
<tbody>
<tr>
<th>Table Header 1</th>
<th>Table Header 2</th>
<th>Table Header 3</th>
</tr>
<tr>
<td>Division 1</td>
<td>Division 2</td>
<td>Division 3</td>
</tr>
<tr class="even">
<td>Division 1</td>
<td>Division 2</td>
<td>Division 3</td>
</tr>
<tr>
<td>Division 1</td>
<td>Division 2</td>
<td>Division 3</td>
</tr>
</tbody>
</table>

<hr />
