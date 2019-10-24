---
layout: post
current: post
cover: assets/images/water.jpg
navigation: True
title: Spring MyBatis와 JPA
date: 2019-07-25 10:18:00
tags: Linux
class: post-template
subclass: 'post tag-fables'
logo: assets/images/ghost.png
author: ghost
published: false
---

## MyBatis
# iBatis Vesus MyBatis
- MyBatis에서는 JDK1.5, Annotation, 다이나믹 SQL을 지원한다.

- MyBatis는 SQL Mapper를 이용하여, 자바의 객체를 SQL문과 연결하여 빠르고 편리하게 데이터베이스에 접근할 수 있게 해준다.

# MyBatis를 프로젝트에 적용하는 방법
- XML 파일을 이용하는 방법 --> 보통 복잡한 쿼리를 사용할 때, 이용된다.
- Annotation을 이용하는 방법 --> 간단한 쿼리를 사용할 때, 이용된다.

## JPA, Hibernate
- JPA를 사용하는 건 ORM을 사용한다는 것과 동일하다. ORM을 사용하면 쿼리문을 보통 직접 작성할 일은 거의 없다.

# JPA 단점
- 성능: SQL문을 직접 작성하는 것보다 성능이 비교적 떨어진다.
- 세밀함: 복잡한 상황에서 데이터를 조작하기가 어렵다. 이를 보완하기 위해, 직접 SQL문을 작성하거나 JPQL을 사용한다.
