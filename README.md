# RESTfull API Level 4

> Still Under Development

### HATEOAS * Semantic HTTP Verbs * Resources / URI * Caching * OAS / Swagger

You can run the application using Maven wrapper
```
$ ./mvnw clean spring-boot:run
```
Installed Maven
```
$ mvn clean spring-boot:run
```
Or using the 'Run' command of your IDE.

##### Example of a RESTfull Resquest/Response

**GET** Request:
```
http://{host}/employees/1
```
***JSON*** Response:
```JSON
{
  "id": 1,
  "name": "Bilbo Baggins",
  "role": "burglar",
  "_links": {
    "self": {
      "href": "http://localhost:8080/employees/1"
    },
    "employees": {
      "href": "http://localhost:8080/employees"
    }
  }
}
```

The interface `ResourceAssembler`, helps to implement HATEOAS using links and the HAL format.
```Java
@Component
public class EmployeeResourceAssembler implements ResourceAssembler<Employee, Resource<Employee>> {

    @Override
    public Resource<Employee> toResource(Employee employee) {
        return new Resource<Employee>(employee,
                linkTo(methodOn(EmployeeController.class).one(employee.getId())).withSelfRel(),
                linkTo(methodOn(EmployeeController.class).all()).withRel("employee")
        );
    }
}
´´´

Me:
- [LinkedIn](https://www.linkedin.com/in/jarades/)
- [GitHub](https://github.com/JARADES-M)
- [HackerRank](https://www.hackerrank.com/Jarades)

References:
- [Chapter 5: Representational State Transfer (REST) - ***Roy Fielding***](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
- [JSON Hypertext Application Language - HAL](https://tools.ietf.org/html/draft-kelly-json-hal-08)
- [RFC 8259 - JSON) Data Interchange Format](https://tools.ietf.org/html/rfc8259)
- [REST APIs must be hypertext-driven](http://roy.gbiv.com/untangled/2008/rest-apis-must-be-hypertext-driven)
- [4 Maturity Levels of REST API Design](https://blog.restcase.com/4-maturity-levels-of-rest-api-design/)
- [Building REST services with Spring](https://spring.io/guides/tutorials/bookmarks/)
- [Caching Data with Spring](https://spring.io/guides/gs/caching/)
- [OpenAPI Specification](https://swagger.io/specification/v2/)
- [Setting Up Swagger 2 with a Spring REST API](https://www.baeldung.com/swagger-2-documentation-for-spring-rest-api)
