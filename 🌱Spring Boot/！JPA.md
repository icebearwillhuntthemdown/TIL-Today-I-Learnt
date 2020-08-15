# JPA(Java Persistent API)
The Java ORM standard for storing, accessing, and managing Java objects in a relational database

### Persistence?
책이나 인터넷 자료를 통해 DB와 통신하는 영역을 영속영역으로 지칭함을 배웠다. 무엇을 영속영역이라고 하는지는 알고 있었는데 왜 영속영역이라고 하는지 궁금해 찾아봤다. [여기](https://www.infoworld.com/article/3379043/what-is-jpa-introduction-to-the-java-persistence-api.html)에 따르면, 영속성Persistence은 객체가 생성된 프로그램의 실행이 종료되고 나서도 계속 유지되는 성질이다.('Persistence means any mechanism by which Java objects **outlive** the application process that created them.') DB에 데이터를 저장하고, 또 저장된 데이터를 불러옴으로써 영속성을 유지하기 때문에 DB와 통신하는 영역을 영속영역이라 지칭하는 모양이다. 

### ORM : Object Relational Mapping
RDBMS를 활용하는 프로젝트의 경우 기존에는 MyBatis와 같은 SQL Mapper를 활용해 SQL 쿼리문을 작성했다. CRUD 기능 하나씩 개별 쿼리가 필요하고, 테이블 수와 테이블간의 관계에 따라 쿼리의 복잡성과 유지보수의 어려움은 가중된다. 이같은 불편함을 해소하기 위해 등장한 것이 ORM, 자바의 경우 JPA이다. 책에서는 이뿐만 아니라, JPA는 **객체지향 프로그래밍 언어와 관계형 데이터베이스의 중간에서 서로 다른 패러다임을 이어주기 위한 기술**이라고 설명한다. JPA는 interface고, 이를 구현하는 implementation은 대표적으로 Hibernate가 있다. Spring에서는 Spring DATA JPA라는 모듈을 이용한다고 한다. Hibernate가 있는데 굳이 Spring에서 Spring DATA JPA를 개발한 것은 특정 implementation, DB에 대한 의존도를 낮추기 위함이라고 한다. JPA 활용시 장점은, 1) CRUD 쿼리를 직접 작성할 필요가 없다😲, 2) 객체지향 프로그래밍을 쉽게 할 수 있다는 것.

```java
@Getter
@NoArgsConstructor
@Entity // JPA annotation, DB의 테이블과 매칭될 엔티티 클래스임을 선언
public class Posts {
  
  @Id // PK field 선언
  @GeneratedValue(strategy = GenerationType.IDENTITY) // PK 생성규칙: auto increment
  private Long id;
  
  @Column(length = 500, nullable = false) // 컬럼임을 선언, 필수는 아님. String default length는 255
  private String title;
  
  @Column(columnDefinition = "TEXT", nullable = false)
  private String content;
  
  //@Column을 선언하지 않아도 필드는 컬럼으로 인식
  private String author;
  
  @Builder
  public Posts(String title, String content, String author){
    this.title = title;
    this.content = content;
    this.author = author;
  }
  
  public void update(String title, String content){
    this.title = title;
    this.content = content;
  }
}
```

### @Builder

