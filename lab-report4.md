# LabReport4- Vim

 *Name: ShengruiChen*
 
 *Email:shc067@ucsd.edu*

 ## Step1: Log into ieng6
 ![Screenshot 2024-02-24 at 10 29 20 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/047780f5-09e0-4984-9ddd-404d40e96f62)

Keys pressed: `ssh <space> shc067@ieng6.ucsd.edu <enter>`
I typed `ssh shc067@ieng6.ucsd.edu` for logging in to my account and press `<Enter>`

## Step2: Clone your fork of the repository from my  Github account
![Screenshot 2024-02-25 at 3 56 20 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/ab8f92f9-b231-4965-92ae-d020d43ca9cd)

Keys pressed: `git <space> clone <space> <command> v <enter>`
Then I clone my fork of the repository from my Github account by copying the SSH clone URLs
link git@github.com:LC0229/lab7-for-lab-report4.git from GitHub.

## Step3: Run the tests, demonstrating that they fail
![Screenshot 2024-02-24 at 10 42 49 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/609ad44e-e021-4c1b-beb7-9c9a2f7c9f29)

Keys pressed: I typed `cd <space> lab7-for-lab-report4` for getting into files and press `<Enter>`. I typed `bash <space> test.sh` for doing the test and press `<Enter>`.


## Step4: Edit the code file to fix the failing test
![Screenshot 2024-02-24 at 11 02 20 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/3efa874c-4985-476b-bfd8-cfa34cdd4b7a)

Keys pressed: `vim <space> L<tab> .java <enter>`
I typed `vim ListExamples.java` for getting into file 

Keys pressed: Type `/index1`, `<enter`for searcching. Then press `*` `*` `*` `*` `*` `*` `*` `*` `*` `*`, since the index1 we want to find is at the 10th of searched words. Then press `l` `l` `l` `l` `l`, since 1 is at the 5th index of the word index1. Press `x` to delete the 1, and press `i` and `2` for inserting the 2 for fixing the bug. Press `<esc>` to the Normal Mode. Type `:wq!` for exiting the file and save changes made.

## Step5: Run the tests, demonstrating that they now succeed
![Screenshot 2024-02-24 at 11 14 53 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/0c98fc4e-8d20-4304-8557-7b3df356de93)

Keys pressed: `<up><up><enter>`, type the `bash test.sh` command is was 2 up in the search history, then it gives us the passed result.

## Step6: Commit and push the resulting change to my Github account

![Screenshot 2024-02-25 at 4 06 35 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/4e97e6eb-105c-4fb4-9078-e873260ee278)

Keys pressed: `git <space> add L <tab> <enter>` , `git <space> commit <space> -m <space> "Editing ListExamples.java"`
Type `git add ListExamples.java`, press `<enter>`
Type `git commit -m "Editing ListExamples.java"` for commit with message.

![Screenshot 2024-02-25 at 4 08 05 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/17f7e29d-0e9e-4be1-96eb-fd7809ba4c45)

Keys pressed: git <space> push <space> origin <space> main
Git push command take commit and save the changes made. main is the branch that saved.



