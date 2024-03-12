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

---

2. Part 2

Some of the interesting command line options for `find` that I found were: `-type`, `-size`, `-mtime`, and `-name`.

* `-type`

```
Philip@w MINGW64 /a/UCSD/docsearch/technical (main)
$ find -type 'd'
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC       
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen     
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```

This is finding all of the directories in the file.

```
Philip@w MINGW64 /a/UCSD/docsearch/technical/911report (main)
$ find -type 'f'
./chapter-1.txt
./chapter-10.txt
./chapter-11.txt
./chapter-12.txt
./chapter-13.1.txt
./chapter-13.2.txt
./chapter-13.3.txt
./chapter-13.4.txt
./chapter-13.5.txt
./chapter-2.txt
./chapter-3.txt
./chapter-5.txt
./chapter-6.txt
./chapter-7.txt
./chapter-8.txt
./chapter-9.txt
./preface.txt
```

This finds all of the files inside of a certain directory, in this case, `911report`.


* `-size`

```
Philip@w MINGW64 /a/UCSD/docsearch/technical (main)
$ find -size '+200k'
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Gen_Account_Office/d01591sp.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Gen_Account_Office/pe1019.txt
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
```

The command `-size` takes an argument of a specific size finds files over a specified size if positive, and returns empty files when negative. 

```
Philip@w MINGW64 /a/UCSD/docsearch/technical/911report (main)
$ find -size '+200k'
./chapter-13.4.txt
./chapter-13.5.txt
./chapter-3.txt
```
Finds all the files over a certain size in the working directory.


* `-mtime`

```
Philip@w MINGW64 /a/UCSD/docsearch/technical (main)
$ find -mtime '0' 
.
./911report
./911report/chapter-1.txt
./911report/chapter-10.txt
./911report/chapter-11.txt
... note 1397 lines omitted...
./plos/pmed.0020281.txt
```

This command finds the files of what day it was modified as the argument. All of the directories and files were created on a certain day, as everything was copied on a single day, there are many files found.

```
Philip@w MINGW64 /a/UCSD/docsearch/technical/911report (main)
$ find -mtime '0' 
.
./chapter-1.txt
./chapter-10.txt
./chapter-11.txt
./chapter-12.txt
./chapter-13.1.txt
./chapter-13.2.txt
./chapter-13.3.txt
./chapter-13.4.txt
./chapter-13.5.txt
./chapter-2.txt
./chapter-3.txt
./chapter-5.txt
./chapter-6.txt
./chapter-7.txt
./chapter-8.txt
./chapter-9.txt
./preface.txt
```

Finds all the files created on a certain day in a directory. 


* `-name`

```
Philip@w MINGW64 /a/UCSD/docsearch/technical (main)
$ find . -name *.txt
./911report/chapter-1.txt
./911report/chapter-10.txt
... note 1397 lines omitted...
./plos/pmed.0020281.txt
```

Finds all of the files that end with .txt. 

```
Philip@w MINGW64 /a/UCSD/docsearch/technical/911report (main)
$ find . -name '*.txt'
./chapter-1.txt
./chapter-10.txt
./chapter-11.txt
./chapter-12.txt
./chapter-13.1.txt
./chapter-13.2.txt
./chapter-13.3.txt
./chapter-13.4.txt
./chapter-13.5.txt
./chapter-2.txt
./chapter-3.txt
./chapter-5.txt
./chapter-6.txt
./chapter-7.txt
./chapter-8.txt
./chapter-9.txt
./preface.txt
```

Finds all of the files that end with .txt in a certain directory. 



Source: https://www.geeksforgeeks.org/find-command-in-linux-with-examples/

Source: https://unix.stackexchange.com/questions/638335/find-command-size-behavior
