# Lab Report 3	
---

1. Part 1

The failure-inducing input. 
```
/**
* The test for the method.
*/
  @Test
  public void testReverseInPlace2(){
    int[] input = {1, 2, 3, 4, 5};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{ 5,4,3,2,1 }, input);
  }

/**
* The method being tested. 
*/

  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

The non-failure-inducing input
```
/**
* The test for the method.
*/
  @Test
  public void testReverseInPlace3(){
    int[] input = {1};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{ 1 }, input);
  }

/**
* The method being tested. 
*/

  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/f9449cdd-6e53-406b-b42e-3ce6b955d593)

The result after running a test that had an incorrect output while the other test passed. 

```
/**
* The method before getting changed.
*/

  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

```
/**
* The method after getting changed.
*/

  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2 ; i += 1) {
      int temp = 0; 
      temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```

The changed method addresses the issues since it can reverse the given array. The length will need to be divided by two to not let the program reverse itself in the process. The `temp` holds the value of `arr[i]` and swaps the value
of `arr[i]` with `arr[arr.length - i - 1]`, and swaps the value at `arr[arr.length - i - 1]` with `temp`.
