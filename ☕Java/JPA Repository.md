# JPA Repository

Spring Data는 CrudRepository, PagingAndSortingRepository, JpaRepository  
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
