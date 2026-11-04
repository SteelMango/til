# Refresher Document

## 1. A unit tests must call the function in order for it to be used 
In the @Test snipped we create an object to be able to use the code in the StringHelper class.

```java
// Sample Source Code 

public class StringHelper {

    public String truncateAInFirst2Positions(String str) {
        if (str.length() <= 2)
            return str.replaceAll("A", "");

        String first2Chars = str.substring(0, 2);
        String stringMinusFirst2Chars = str.substring(2);

        return first2Chars.replaceAll("A", "")
                + stringMinusFirst2Chars;
    }
}

```

``` java
@Test
public void test1() {
    StringHelper = new StringHelper();

    String actual = helper.truncateAInFirst2Positions("AACD");
    String expected = "CD";

    assertEquals(expected,actual);
}
```

# 2. Names of the tests should include the function name and what the conditions it is given 

```java
@Test
public void testTruncateAInFirst2Positions_validInput(){}
```

# 3. Tests should be atomic
If a test requires more than one conditions, another tests should be created for the exact condition. 

# 4. For every class that is tested, make sure that their is a seperate test file for that exact file.