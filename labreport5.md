# LAB REPORT 5 #

The following is my codeL

```
# Create your grading script here

CPATH = ".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar"

set -e (stop running when ecounters errors)

rm -rf student-submission
#step 1
mkdir student-submission
git clone $1 student-submission
echo "We are done cloning!!! Part 1 of 3 achieved."

#step 2
cp TestListExamples.java student-submission
cd student-submission

if [[-f "ListExamples.java"]]
    then 
        echo "File Found"
        echo "Excellent! Part 2 of 3 achieved."
    else
        echo "Wrong file submitted"
        exit 0
fi 

#step 3
#cp TestListExamples.java /student-submission

#step 4
javac -cp $CPATH *.java
java -cp org.junit.runner.JUNITCORE TestListExamples > out.txt 2>error.txt
cd student-submission

if [[$? -eq 0]]
    then 
        echo "Compile Succesfull and all tests passed!"
        echo "3 of 3 points achieved!"
        cat testOutput.txt
    else 
        echo "Last run test failed" 
        exit 0
fi 

#step 5
#java -cp org.junit.runner.JUNITCORE TestListExamples > file2.txt
#if [[grep "passed" file2.txt]]
#    then
#       "Grade A"
#   else 
#       "Tests have failed"
fi
```

## TRACE ##

This code i
