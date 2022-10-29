# LAB REPORT 3 #

## Implementation 1: find -perm 777 ##
Explanation: This command finds files with 777 permissions. 777 permission are the ability to read, write and execute permission to the owner, group and public. We are able to add different codes at the end of perm in order to find files with different codes. This is useful as many times we have certain files that are specfically for public use but may be scattered throughout different folders; through finding files like this we can make changes to groups of files with this specific access all at once. This would be useful in a government setting or enterprise situation. The following are three examples of inputs and outputs using -perm 777. 

**Example 1**
Input:
```
[cs15lfa22qs@ieng6-201]:911report:199$ find -perm 777
```
Output:
```
.
```

**Example 2**
Input:
```
[cs15lfa22qs@ieng6-201]:911report:200$ cd ..
[cs15lfa22qs@ieng6-201]:technical:201$ cd government
[cs15lfa22qs@ieng6-201]:government:202$ find -perm 777
```
Output:
```
.
./About_LSC
./Alcohol_Problems
./Env_Prot_Agen
./Gen_Account_Office
./Media
./Post_Rate_Comm
[cs15lfa22qs@ieng6-201]:government:203$ cd ..
```

**Example 3**
Input:
```
[cs15lfa22qs@ieng6-201]:plos:207$ cd ..
[cs15lfa22qs@ieng6-201]:technical:208$ find -perm 777
```
Output:
```
.
./911report
./biomed
./government
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./government/Post_Rate_Comm
./plos
```

## Implementation 2: find ! <command> ##
**Explanation:** In order to find files that do not pertain to the desired filter, we can just add an "!" in front of it. I show this below reagrding files that do NOT have 777 permissions, are not empty and do not contain .txt. I find this to be one of the most useful commands. Say we want to make an edit to something at large but don't want to do it to say empty files or one specific files or pdf files etc. We are able to still make that edit or find those files exlcuding a certain group through using this function or alteration to find. The following are three different implementations of this command. 

**Example 1:  find ! -perm 777**

Input:
```
[cs15lfa22qs@ieng6-201]:biomed:212$ cd ..
[cs15lfa22qs@ieng6-201]:technical:213$ cd 911report
[cs15lfa22qs@ieng6-201]:911report:214$ find ! -perm 777
```

Output:
```
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

**Example 3: do not contain name**

Input:
```
[cs15lfa22qs@ieng6-201]:technical:230$ find ! -name "*.txt"
```

Output:
```
.
./911report
./biomed
./government
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./government/Post_Rate_Comm
./plos
```

## Implementation 3: find -size +<X>b/-<X>b ##
**Explanation**: Through this variation of the find command one can find files with with size larger than something, smaller than a size or in between a range. In this case I am using b which stands for bytes, but one can also use M, G etc. to represent different byte sizes. This is also a useful command as many times we can characterize files by their sizes, i.e. can infer to divide up content when we do not have any pattern on name etc. solely by thier expected size. This can truly help us find files through size pattern when we don't have other information. 

**Example 1: finding files bigger thatn 500 bytes**

Input:
```
[cs15lfa22qs@ieng6-201]:911report:246$ find -size +500b
```

Output:
```
./chapter-13.4.txt
./chapter-13.5.txt
./chapter-3.txt
```
**Example 2: finding files smaller thatn 5 bytes**

Input:
```
cs15lfa22qs@ieng6-201]:government:256$ find -size -5b
```

Output:
```
./Media/Campaign_Pays.txt
./Media/Court_Keeps_Judge_From.txt
./Media/Fire_Victims_Sue.txt
./Media/It_Pays_to_Know.txt
./Media/Justice_requests.txt
./Media/Lawyer_Web_Survey.txt
./Media/Self-Help_Website.txt
```
**Example 3: finding files between **

Input:
```
[cs15lfa22qs@ieng6-201]:plos:262$ find -size +40b -size -50b 
```

Output:
```
./journal.pbio.0020053.txt
./journal.pbio.0020054.txt
./journal.pbio.0020113.txt
./journal.pbio.0020161.txt
./journal.pbio.0020267.txt
./journal.pbio.0020347.txt
./journal.pbio.0020406.txt
./journal.pbio.0030137.txt
./pmed.0010045.txt
./pmed.0010066.txt
./pmed.0020015.txt
./pmed.0020061.txt
./pmed.0020140.txt
```