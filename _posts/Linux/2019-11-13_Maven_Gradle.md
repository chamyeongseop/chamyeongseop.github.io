---
layout: post
current: post
cover: assets/images/sky.jpg
navigation: True
title: Maven과 Gradle 정리
date: 2019-11-07 09:00:00
tags: JAVA
class: post-template
fonts: Nanum Gothic
subclass: 'post tag-fables'
author: akas
published: false
---
포스트 작성을 위해 일부 내용은 아래의 블로그에서 내용을 차용하였습니다.
출처 : https://bkim.tistory.com/13


# Maven
- 자바 프로젝트 관리 도구이며, 아파치 라이센스로 배포되는 오픈소스 S/W이다.
- 네트워크를 통해 라이브러리 뿐만 아니라, 연관 된 라이브러리까지 업데이트를 자동으로 해준다.

# Gradle
- Groovy를 이용한 빌드 자동화 시스템이다.
- Ant와 Maven의 장점을 모았으며, 유연한 범용 빌드 도구임과 동시에 변환이 가능한 컨벤션 프레임 워크이다.
- 원격 저장소나, pom, ivy 파일 없이 연결되는 의존성 관리 방식을 지원한다.

# Maven과 Gradle 성능 비교
- 스크립트 길이와 가독성 측면에서는 Gradle이 우수하다.
- Gradle이 캐시를 사용하기 때문에 테스트를 반복할 시에, 빌드와 테스트 실행 속도가 빠르다.
- 의존성이 늘어날수록 성능과 스크립트 품질의 차이가 많이 난다.
