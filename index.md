# Lab Report 4
---

Step 4: 

![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/a34b94eb-626a-4cc5-b359-8c98c1afbba8)

First I have to ` ssh ` into the ieng6 server, which will not need a password. 

Keys Pressed: ` ssh yad013@ieng6.ucsd.edu `

Step 5:

![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/674d0684-1f8f-490a-a56b-cf3a2a052735)

Then I will need to use `git clone` in order to clone the forked repository. 

Keys Pressed: `git clone git@github.com:Omeggos/lab7.git`

Step 6:

![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/992a05f2-b51b-49d8-9228-dfa21ca0826c)

Using `bash test.sh` we are able to run the tests and demonstrate that they will fail. But first, I will need to cd into the directory. 

Keys pressed: `cd lab7/`, `bash test.sh`

Step 7: 

![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/2f967506-a58e-4588-b044-9a5044d04eec)

![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/93a215e7-9386-4f42-b7c2-6542a10031f0)

We will use `vim` in order to both access the file and change the contents of the file from the command line. Then certain keystrokes will be used to both navigate and change the contents of the file. We know that the error occurs on line 43, therefore we can use the following key presses to fix the file. 

`vim ListExamples.java`, `4 3 <enter> e a <backspace> 2 <esc> : w q`

Step 8: 

![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/edcccac7-7492-489b-a3ce-af3768a07609)

Now we will use `bash test.sh` to check if the tests are working.

Keys pressed: `<up> <up>`

Step 9:

![image](https://github.com/Omeggos/cse15l-lab-reports/assets/105466539/2cf717af-fca3-42fd-9e4d-f96302265b1c)

This last step will utilize certain `git` commands in order to `add`, `commit`, and `push`. `add` adds the changes to the files, `commit` commits the changes, and `push` pushes the changes back to github.

Keys pressed: `git add ListExamples.java`, `git commit -m 'fixed`, `git push`
