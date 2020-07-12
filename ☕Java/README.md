# ☕ Java
자바 관련 학습 내용을 기록할 폴더이다. 가장 먼저 배운 언어이고, 그래서 가장 많이 다룬 언어이지만 아직 부족한 부분이 많다. 빠진 부분 채워나가면서 자신감을 얻어야지! Piano, piano!


### [Introduction to Java](https://hyperskill.org/learn/step/3500)
The key feature of Java is **platform independence**, meaning the same Java program can be run on multiple platforms without any changes. This principle is also known as "Write Once, Run Anywhere", WORA in short.

There are some other important features like...
* A simple and clear syntax : easy to read and are widely used in other languages.
* Garbage collection(GC) : garbage collector automatically cleans memory from unused objects during runtime.
  * Unlike Java, in C/C++ programmer is responsible for both creation and destruction of objects. Neglection on the destruction of unused objects, it can bring about memory shortage, which can lead to abnoraml termination of the entire program.
  * In Java, garbage collector takes the destruction job for programmer, freeing heap memory by destorying unreachable objects which don't have any reference to them.
* Object-Oriented Programming(OOP) : almost every part of a program is an object, therefore, a program itself can be considered a set of interacting objects. Below are the 4 pillars of OOP.
  * Encapsulation 
  * Inheritance
  * Polymorhpism
  * Abstraction
* Support other modern paradigms
  * Generic programming
  * Concurrent programming
  * Functional programming
