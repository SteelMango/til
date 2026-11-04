
# 1. Can not use normal assertEquals to compare arrays
It compares the memory location rather than the actual values inside the arrays. 

```java
// Given we have the two arrays with the same values : ar1, ar2, 

public class ArraysTest {
    @Test
    @DisplayName("Comparing two arrays to see if they are the same")
    public void testCompareArray() {
        int[] ar1 = {1,2,3};
        int[] ar2 = {1,2,3};

        assertEquals(ar1,ar2);
        // Returns a failing test
             //java.lang.AssertionError: 
             //Expected :[I@735b5592
              //Actual   :[I@58651fd0
    }
}

```

# 2. Use assertArrayEquals(x,y); to compare 

```java
public class ArraysTest {
    @Test
    @DisplayName("Comparing two arrays to see if they are the same")
    public void testCompareArray() {
        int[] ar1 = {1,2,3};
        int[] ar2 = {1,2,3};

        assertArrayEquals(ar1,ar2);
        // Output: 1 Passing Test 
    }
}
```

# 3. How the assertArrayEquals work 
Given two arrays to see if they are equal, the code will check if the value at the index starting 0 is the same, if they are it will move to the next index to count
```java
// Despite having the same values, this will be a failing test
array1 = 1,2,3
array2 = 1,3,2

// This will be a passing test
array1 = 1,2,3
array2 = 1,2,3
```