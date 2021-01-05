---
title: "Static method vs Istance method"
date: 2021-01-05
tags: java
---

## Static method VS Instance method

```html
class MyMath2 {
      long a, b;

      long add() { //인스턴스 메소드
          retun a + b;
      }

      static long add(long a, long b) { //클래스메소드(static메소드)
          return a + b;// a,b는 지역변수(Local Variable)
      }
  }
```
> 가장 큰 차이점은 객체 생성 여부

Static method는 클래스 변수와 마찬가지로
객체를 생성하지 않고 클래스명.메서드명으로 호출 가능하다.

Instance method는 Static method와는 달리, 반드시 객체를 생성한 후에 호출 가능하다.
즉, Instance method는 인스턴스가 반드시 존재해야만 사용할 수 있다.

```html
class MyMath2Test {
      public static void main(String args[]){
          
          System.out.print(MyMath2.add(200L, 100L));//클래스메소드 호출
          //클래스 메소드는 객체 없이 호출 가능
          
          MyMath2 mm = new MyMath2(); //인스턴스 생성
          mm.a = 200L;
          mm.b = 100L;
          System.out.println(mm.add()); //인스턴스메소드 호출
      }
  }
```

>Static method는 인스턴스를 생성하지 않아도 사용할 수 있다.
Static이 붙은 메서드는 클래스가 메모리에 올라갈 때 자동으로 생성되기 때문이다.

> Static method는 인스턴스 변수를 사용할 수 없다.
Static method는 인스턴스 생성 없이 호출 가능하므로
Static method가 호출되었을 때, 인스턴스가 존재하지 않을 수도 있다.
따라서, Static method에서 인스턴스 변수를 사용해서는 안된다.

이와 반대로,Instance method에서는 Static이 붙은 멤버들을 사용하는 것이 언제나 가능하다.
(인스턴스 변수가 존재한다는 것은 Static 변수가 이미 메모리에 존재한다는 것을 의미하기 때문)
