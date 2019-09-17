---
layout: post
current: post
cover: assets/images/wave.jpg
navigation: True
title: JAVA의 다형성(Polymorphism)과 동적바인딩
date: 2019-09-17 09:00:00
tags: Java
class: post-template
fonts: Nanum Gothic
subclass: 'post tag-fables'
author: akas
published: true
---
# 다형성
- "객체지향"에는 4가지 중요한 개념이 있다. 추상화, 캡슐화, 상송 그리고 다형성이다.
- 아래의 코드를 통해, 다형성 및 동적 바인딩의 개념을 살펴보자.


{% highlight java %}
class Polymorphism{
  public static void main(String args[]){
    Person student = new Student();
    student.show();
  }
}
class Person{
  void show(){
    System.out.println("Person")
  }
}
class Student extends Person{
  void show(){
    System.out.println("Student");
  }
}
{% endhighlight %}

참조 변수 student는 Person 객체를 참조하고 있다. 따라서, Person 내의 show() 메소드가 호출이 되어야하지만, 동적바인딩을 통해 런타임 시점에 객체 타입을 기준으로 실행될 함수를 호출한다.
즉 실행되는 시점에서는  Student 객체가 생성되어, 해당 객체의 show() 함수를 호출한다.

정리하자면, 다형성이 적용될 때, 참조 변수 student는 컴파일 시점과 런타임 시점에서 참조하는 함수가 다른 것이다.

게시글 참조 : https://brunch.co.kr/@mystoryg/60
