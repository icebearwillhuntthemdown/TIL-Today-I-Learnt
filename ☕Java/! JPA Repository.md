# JPA Repository

Spring Data는 CrudRepository, PagingAndSortingRepository, JpaRepository 인터페이스를 제공한다. PagingAndSortingRepository는 CrudRepository를, JpaRepository는 PagingAndSortingRepository를 상속하기 때문에, 결국 JpaRepository를 쓰면 나머지 두 인터페이스의 함수에도 접근할 수 있다. JPA는 Java Persistence API의 줄임말. 말 그대로 자바가 제공하는 영속성 관련 API로, 데이터 접근 및 가공 작업을 훨씬 수월하게 해준다.     
https://www.baeldung.com/spring-data-repositories


## Optional<T>
    - get()
    - orElse(T other)
    - orElseThrow(exception)  
https://dbbymoon.tistory.com/3

## Serializable
 - Serialization : the process of converting data used by an application to a format(e.g. json) that can be transferred over a network or stored in a database or a file.  
    e.g.) Kotlin object => json

Deserialization : the opposite process of reading data from an external source and converting it into a runtime object. 
    e.g.) json => Kotlin object
