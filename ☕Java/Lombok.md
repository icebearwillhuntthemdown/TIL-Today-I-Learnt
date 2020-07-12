# Lombok

롬복은 어노테이션으로 Getter/Setter, Constructor 등의 메소드 작성을 대신하는 편리한 자바 라이브러리다. 교육과정 중 한 강사님은 롬복을 소개해주시고 적극적으로 쓰셨는데, 또 다른 강사님은 실무에서는 롬복을 쓰면 다른 개발자에게 민폐라는 인식도 있다며 지양하라고 하셨다. 찬반 의견이 1:1이라 롬복을 쓰는 게 좋은 관행인지 아닌지 아리송했는데, [요즘 공부하고 있는 책](http://www.yes24.com/Product/Goods/83849117)에서 롬복 사용을 권장해서 2:1이 됐다. 책에서는 **해당 클래스의 의존성 관계가 변경될 때마다 생성자 코드를 계속해서 수정하는 번거로움을 해결하기 위해** 롬복을 쓴다고 말하는데, 정말 그렇다.  
사실 롬복을 쓰거나 쓰지 않거나 엄청난 차이가 발생하는 건 아니다. 롬복 사용을 지양하라고 하셨던 강사님은 Getter/Setter, Constructor 등의 메소드가 명시적으로 보이지 않아 다른 개발자가 작성한 코드를 볼 때 헷갈릴 수 있음을 이유로 드셨다. 틀린 말은 아닐 것이다. 하지만 롬복은 반복적인 메소드 작성과 변동사항 발생 시 연관 메소드를 일일이 수정하는 수고를 없애준다. 꼭 치명적인 문제가 발생해서 대처하는 게 아니라, 지금보다 조금이나마 더 나아지기 위해 노력하는 것. 난 이래서 개발이 좋다.   


### [Annotation List](https://projectlombok.org/features/all)

* @Getter/@Setter : 해당 클래스의 필드에 대한 Getter/Setter를 만든다.
* @ToString : 해당 클래스의 필드를 출력하는 ToString() 메소드를 만든다. 
* @NoArgsConstructor : 해당 클래스의 디폴트 생성자를 만든다.
* @RequiredArgsConstructor : 해당 클래스의 필드 중 final로 선언된 필드만을 포함하는 생성자를 만든다. 
* @AllArgsConstructor : 해당 클래스의 모든 필드를 포함하는 생성자를 만든다.
* @Data : @Getter, @Setter, @ToString, @EqualsAndHashCode, @RequiredArgsConstructor를 한 번에!
* @Builder : Builder 패턴을 보다 쉽게 만들 수 있게 해준다. 빌더 패턴 자체에 대한 정리는 따로 해야겠다.
> @Builder lets you automatically produce the code required to have your class be instantiable with code such as:
```java
Person.builder().name("Adam Savage").city("San Francisco").job("Mythbusters").job("Unchained Reaction").build();
```
