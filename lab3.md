# Lab Report 3
---
## find command
## -size n
The -size command specifies the size (in kb) of a file you are looking for. Additionally, the + indiciates files that are larger than the size that while - indicates files less than that. This command was found at this [website](https://kb.iu.edu/d/admm).
```
$ find ./technical -size +500
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./technical/government/Gen_Account_Office/d01591sp.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.tx
```
This example is getting any file with a size of at least 500 bytes which is helpful for weeding out small files with minimal text that you may want to ignore
```
$ find ./technical -size 100
./technical/biomed/1471-2377-3-4.txt
./technical/biomed/gb-2003-4-6-r39.txt
./technical/biomed/gb-2003-4-3-r20.txt
```
This example is getting any file with a size of exactly 100 bytes which is helpful for gathering files with a certain amount of characters for sorting or organization
## -iname n
The -iname command specifies a name of a file to look for that is not case sensitive. Any file with the same letters regardless of the capitalization will be returned. This command was found at this [website](https://www.tutorialspoint.com/unix_commands/find.htm).
```
$ find ./technical -iname CHAPTER-1.txt
./technical/911report/chapter-1.txt
```
This example is getting any files with the same title but in all caps which is beneficial when finding non case sensitive materials.
```
$ find ./technical -iname PrEfAcE.txt
./technical/911/report/preface.txt
```
This example is getting any files with the same title but in randomized caps which is beneficial for typos which may be missed otherwise
## -type n
The -type file specifies files of a specific type such as d for directory or f for plain text. Non existent file types will bring up errors. This command was found at this [website](https://www.softwaretestinghelp.com/find-command-in-unix/)
```
$ find ./technical -type d
./technical
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/government/Media
./technical/plos
./technical/biomed
./technical/911report
```
This usage gets all the directories which is helpful for listing out all the possible paths a file could be in.
```
$ find ./technical -type f
... a bunch of lines ...
./technical/911report/chapter-9.txt
./technical/911report/chapter-8.txt
./technical/911report/preface.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
```
This usage just gets all the text files which is helpful as it lists out all the files without any of the directories taking up lines
## -o
The -o allows for querying multiple searches together. This command was found at this [website](https://unix.stackexchange.com/questions/50612/how-to-combine-2-name-conditions-in-find)
```
$ find ./technical \( -name "chapter-10.txt" -o -name "chapter-9.txt" \)
./technical/911report/chapter-9.txt
./technical/911report/chapter-10.txt
```
This usage queries two different file nanes which is beneficial for gathering similar files with specific parameters
```
$ find ./technical \( -size 80 -o -size +300 \)
./technical/government/About_LSC/commission_report.txt
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Env_Prot_Agen/tech_adden.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./technical/government/Gen_Account_Office/pe1019.txt
./technical/government/Gen_Account_Office/d01591sp.txt
./technical/biomed/1471-2164-4-21.txt
./technical/biomed/1471-2091-3-18.txt
./technical/biomed/1472-6785-2-7.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
```
This usage queries two different file size ranges which is beneficial for using specific parameters on files of varying sizes such as files that are too large or too small.
