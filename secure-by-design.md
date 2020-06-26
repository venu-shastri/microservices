#  Microservices Security Design Patterns

## Be Secure By Design 
Secure by design means that you bake security into your software design from the beginning. If you have user input, sanitize the data and remove malicious characters
```java
//Bad Design
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
``` java
// Good Design
public class Username {
   private static final int MINIMUM_LENGTH = 4;
   private static final int MAXIMUM_LENGTH = 40;
   private static final String VALID_CHARACTERS = "[A-Za-z0-9_-]+";

   private final String value;

   public Username(final String value) {
      notBlank(value);

      final String trimmed = value.trim();
      inclusiveBetween(MINIMUM_LENGTH,
                       MAXIMUM_LENGTH,
                       trimmed.length());
      matchesPattern(trimmed,
                     VALID_CHARACTERS,
                     "Allowed characters are: %s", VALID_CHARACTERS);
      this.value = trimmed;
   }

   public String value() {
      return value;
   }
}

public class User {
   private final Long id;
   private final Username username;

   public User(final Long id, final Username username) {
      this.id = notNull(id);
      this.username = notNull(username);
   }
}
```



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3OTk3NDM2MjddfQ==
-->