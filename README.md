# RESTfull API Level 3

### HATEOAS * Semantic HTTP Verbs * Resources / URI * Caching * OAS / Swagger

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

Me:
- [LinkedIn](https://www.linkedin.com/in/jarades/)
- [GitHub](https://github.com/JARADES-M)
- [HackerRank](https://www.hackerrank.com/Jarades)

Refs:
- [OpenAPI Specification](https://swagger.io/specification/v2/)
- [Chapter 5: Representational State Transfer (REST) - ***Roy Fielding***](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
- [Building REST services with Spring](https://spring.io/guides/tutorials/bookmarks/)
- [4 Maturity Levels of REST API Design](https://blog.restcase.com/4-maturity-levels-of-rest-api-design/)
- [Setting Up Swagger 2 with a Spring REST API](https://www.baeldung.com/swagger-2-documentation-for-spring-rest-api)
- [Caching Data with Spring](https://spring.io/guides/gs/caching/)