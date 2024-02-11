# LabReport3

 *Name: ShengruiChen*
 
 *Email:shc067@ucsd.edu*

## Part1-Bugs


* failure-inducing input

```java

import static org.junit.Assert.*;
import org.junit.*;

@Test
  public void testReversed2() {
    int[] input2 = { 1,2,3};
    assertArrayEquals(new int[]{ 3,2,1}, ArrayExamples.reversed(input2));
```


* input that doesn't induce a failure
 ```java
@Test
  public void testReversed1() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

* Symptom
  
![Screenshot 2024-02-10 at 8 38 17 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/2d044ba8-488d-41b3-84b1-63fe5624d837)

![Screenshot 2024-02-10 at 8 38 27 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/96c73408-088e-47de-a538-dbd9a8968a9d)

  
* Before
```java

static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      //newArray[i] = arr[arr.length - i - 1];
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

* After
```java

  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```



