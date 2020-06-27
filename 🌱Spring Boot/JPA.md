# JPA(Java Persistent API)
The Java ORM standard for storing, accessing, and managing Java objects in a relational database

### Persistence?
책이나 인터넷 자료를 통해 DB와 통신하는 영역을 영속영역으로 지칭함을 배웠다. 무엇을 영속영역이라고 하는지는 알고 있었는데 왜 영속영역이라고 하는지 궁금해 찾아봤다. [여기](https://www.infoworld.com/article/3379043/what-is-jpa-introduction-to-the-java-persistence-api.html)에 따르면, 영속성Persistence은 객체가 생성된 프로그램의 실행이 종료되고 나서도 계속 유지되는 성질이다.('Persistence means any mechanism by which Java objects *outlive* the application process that created them.') DB에 데이터를 저장하고, 또 저장된 데이터를 불러옴으로써 영속성을 유지하기 때문에 DB와 통신하는 영역을 영속영역이라 지칭하는 모양이다. 

### ORM Object Relational Mapping

