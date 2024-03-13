# Lab Report 5

---

* Part 1:

Original post 

Hello! I am having problems with the compilation step of my code. I have tried looking at the TestListExamples class file and tried changing the headers to no avail. This happens to all of the test cases that I have passed in, and I have no idea why this is not working. I have attached the results that I have been getting due to compilation issues down below. 

![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/4a45216f-5dc7-43c0-a6ce-3d3a3756cbba)

TA response: 

Hello, I would be glad to help you out! I wanted to ask what operating system are you using on your device. If you are on Windows please look at your grade.sh file and check that CPATH uses semicolons instead of colons. Otherwise please check your other files to see that there are no typos. Please come to office hours if you still need help! 

Student response:

Thank you for the response, I am using a Windows device, and after changing the colons to semicolons for CPATH it started to compile! Thank you so much!

![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/597f8075-a16e-43f9-825d-d0e9258a18fe)

I think the compilation bug came from the fact that there are slight differences between the Windows and Mac operating systems, and Windows uses semicolons to access the lib folder, whilst Mac uses colons instead. 

The files needed were `TestListExamples.java` and `grade.sh` as those were the two files that needed to be looked at and fixed.
The directories needed were the ones that were passed in when the contents inside the GitHub repositories were copied. 

The `grade.sh` before change 

```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf student-submission
rm -rf grading-area
rm -rf temp-files

mkdir grading-area
mkdir temp-files

git clone $1 student-submission
echo 'Finished cloning'

PASSED=0
# Draw a picture/take notes on the directory structure that's set up after
# getting to this point

# Then, add here code to compile and run, and do any post-processing of the
# tests

if [ -f "student-submission/ListExamples.java" ]; then
    echo "file found!"
    PASSED=$(($PASSED+1));

else  
    echo "ListExamples.java not found!"
    
fi

cp -r lib grading-area

cp student-submission/ListExamples.java grading-area/

cp TestListExamples.java grading-area/

cd grading-area

TEMP=$(javac -cp $CPATH *.java)
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > ../temp-files/results.txt



if [[ $? -ne 0 ]]
then
    echo "Compile error!"
    echo $TEMP
    exit 1
else
    echo "Compiled successfully!"
    PASSED=$(($PASSED+1));
fi

grep "Tests run" ../temp-files/results.txt > ../temp-files/newtemp.txt
grep -o '[0-9]' ../temp-files/newtemp.txt|sed -n '1p' > ../temp-files/first.txt
grep -o '[0-9]' ../temp-files/newtemp.txt|sed -n '2p' > ../temp-files/second.txt

let "b = 2"

#echo "Your score is:" $PASSED "/" $b

FIRST=$(cat ../temp-files/first.txt| sed -n '1p')
echo $FIRST
SECOND=$(grep -o '[0-9]' ../temp-files/newtemp.txt|sed -n '2p')
echo $SECOND
echo "Your score is:" $PASSED "/" $b

```

The `grade.sh` after change 

```
CPATH='.;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar'

rm -rf student-submission
rm -rf grading-area
rm -rf temp-files

mkdir grading-area
mkdir temp-files

git clone $1 student-submission
echo 'Finished cloning'

PASSED=0
# Draw a picture/take notes on the directory structure that's set up after
# getting to this point

# Then, add here code to compile and run, and do any post-processing of the
# tests

if [ -f "student-submission/ListExamples.java" ]; then
    echo "file found!"
    PASSED=$(($PASSED+1));

else  
    echo "ListExamples.java not found!"
    
fi

cp -r lib grading-area

cp student-submission/ListExamples.java grading-area/

cp TestListExamples.java grading-area/

cd grading-area

TEMP=$(javac -cp $CPATH *.java)
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > ../temp-files/results.txt



if [[ $? -ne 0 ]]
then
    echo "Compile error!"
    echo $TEMP
    exit 1
else
    echo "Compiled successfully!"
    PASSED=$(($PASSED+1));
fi

grep "Tests run" ../temp-files/results.txt > ../temp-files/newtemp.txt
grep -o '[0-9]' ../temp-files/newtemp.txt|sed -n '1p' > ../temp-files/first.txt
grep -o '[0-9]' ../temp-files/newtemp.txt|sed -n '2p' > ../temp-files/second.txt

let "b = 2"

#echo "Your score is:" $PASSED "/" $b

FIRST=$(cat ../temp-files/first.txt| sed -n '1p')
echo $FIRST
SECOND=$(grep -o '[0-9]' ../temp-files/newtemp.txt|sed -n '2p')
echo $SECOND
echo "Your score is:" $PASSED "/" $b

```

The `TestListExamples.java` stayed the same before and after as nothing within it needed to be changed. The same goes for the directories as those do not need to be changed. 

The full command line that I ran to trigger the bug was `bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected`.

In order to fix the bug, in CPATH, CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar', change the colons to semicolons for windows operating systems in order to access the lib directory and in return the JUnit testing files. 

---

* Part 2:

There were so many cool things that I learned during the second half of this class. I think the most interesting thing that I learned has to be the `vim` command as it allows for only command line usage to edit files and directories which I think was extremely interesting. I think the thing I enjoyed most about this part of class has to be the command line commands and their usages, like making new directories, new files, and editing those files from the command line without needed to see the files on a sidebar. Furthermore learning about bash scripts was also quite interesting, as it sped up the process of testing by more than twofold, which was quick an eyeopener for me. 
