# Lab Report 1	

* ``cd`` commands

1. No arguments

   ![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/5da483c8-d892-447a-9277-ac505461b4f1)
   
   The working directory when the code was run, was in /home/lecture1/messages, and it ends in /home.
   
   When calling `cd` without any arguments, it will be brought back to the home directory.
   
   The output was not an error.
   

2. Directory as an argument

   ![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/92b17b8f-b80c-4106-95ee-73f82fa60428)
   
   The working directory when the code was run, was in /home, and it ended in /home/lecture1.
   
   When calling `cd` with a directory as an argument, the working directory will now be in the directory that was called as an argument.

   The output was not an error.

3. File as an argument

   ![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/c61345ae-ac27-46df-b751-dabea6e8680b)

   The working directory when the code was run, was in /home/lecture1, and it ended in /home/lecture1.
   
   When calling `cd` with a file as an argument, it will not be able to `cd` into the file and instead stay in the same working directory as it cannot `cd` into a file, only directories.

   The output was an error because you cannot `cd` into a file. 

---

* `ls` commands

1. No arguments
 
   ![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/0911cbd8-53c8-42e4-89a1-b9cefe13397b)

   The working directory when the code was run, was in /home/lecture1, and it ended in /home/lecture1.

   When calling ls with no arguments, it will list the contents of the current working directory. 

   The output was not an error.
  
2. Directory as an argument

   ![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/d0ea9544-110d-4927-85fc-33064b005ac6)

   The working directory when the code was run, was in /home/lecture1, and it ended in /home/lecture1.

   When calling ls with a directory as an argument, it will list the contents within the directory that was the argument.

   The output was not an error.
   
3. File as an argument

   ![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/d3ea`cd`d4-a3dc-4412-9fd9-e0dcbf51e6f4)

   The working directory when the code was run, was in /home/lecture1, and it ended in /home/lecture1.

   When calling ls with a file as an argument, it will only list the file that was inputted as the argument.

   The output was not an error.

 
---

* `cat` commands

1. No arguments

   ![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/d6716f51-8a0a-4f6c-99f9-e305c289705b)

   The working directory when the code was run, was in /home/lecture1, and it ended in /home/lecture1.

   When calling cat with no argument, all sequential entries into the command line will be returned.

   The output was not an error.

2. Directory as an argument

   ![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/d5ef0c1d-66d7-43bd-a399-35f0de973af9)

   The working directory when the code was run, was in /home/lecture1, and it ended in /home/lecture1.

   When calling cat with a directory as an argument, there will be an error thrown saying that the argument was a directory and nothing will be printed.

   The output was an error as the cat command is to read a file and then output the contents of the file, it cannot do the same to a directory. 

4. File as an argument

   ![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/d4d3e8c6-a5d5-4d1f-bfda-711c9abc6a32)

   The working directory when the code was run, was in /home/lecture1, and it ended in /home/lecture1.

