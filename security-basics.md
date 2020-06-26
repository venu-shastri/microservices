#  Microservices Security Design Patterns

## Be Secure By Design 
Secure by design means that you bake security into your software design from the beginning. If you have user input, sanitize the data and remove malicious characters
```java
```
public class User {
   private final Long id;
   private final String username;

   public User(final Long id, final String username) {
      this.id = id;
      this.username = username;
   }

   // ...
}
```
```



<!--stackedit_data:
eyJoaXN0b3J5IjpbNzYxNDQ4MzA5LDc3MjQzODEzNF19
-->