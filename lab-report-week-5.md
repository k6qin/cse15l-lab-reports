# **Week 5 Lab Report**
> *By Ken Qin*
---
* Researching Commands

The command I choose to research about is `grep`, I have found three alternative ways to use this command: `grep -c`, `grep -L`, and `grep -e`. Which will be explained in details below. 

* `grep -c`
```
qinken@Kens-MBP skill-demo1 % grep -c "Introduction" */government/Post_Rate_Comm/*.txt
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:0
technical/government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:1
technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:0
technical/government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt:1
technical/government/Post_Rate_Comm/Cohenetal_Scale.txt:2
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:0
technical/government/Post_Rate_Comm/Gleiman_EMASpeech.txt:0
technical/government/Post_Rate_Comm/Gleiman_gca2000.txt:0
technical/government/Post_Rate_Comm/Mitchell_6-17-Mit.txt:1
technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt:0
technical/government/Post_Rate_Comm/Mitchell_spyros-first-class.txt:1
technical/government/Post_Rate_Comm/Redacted_Study.txt:0
technical/government/Post_Rate_Comm/ReportToCongress2002WEB.txt:0
technical/government/Post_Rate_Comm/WolakSpeech_usps.txt:0
```
Here, we can look at a command-line option that only ouputs the count of matching line with `grep -c`. This is useful when we want to find how many lines in the files that matches our string. 
```
qinken@Kens-MBP skill-demo1 % grep -c "war" */911report/*.txt                         
technical/911report/chapter-1.txt:57
technical/911report/chapter-10.txt:19
technical/911report/chapter-11.txt:37
technical/911report/chapter-12.txt:31
technical/911report/chapter-13.1.txt:15
technical/911report/chapter-13.2.txt:49
technical/911report/chapter-13.3.txt:18
technical/911report/chapter-13.4.txt:24
technical/911report/chapter-13.5.txt:90
technical/911report/chapter-2.txt:29
technical/911report/chapter-3.txt:86
technical/911report/chapter-5.txt:25
technical/911report/chapter-6.txt:40
technical/911report/chapter-7.txt:26
technical/911report/chapter-8.txt:30
technical/911report/chapter-9.txt:31
technical/911report/preface.txt:2
```
Similarly, we can use `-c` command-option to search for keywords in specific files. As see from the example above, if we want to see how many times the keyword " war" appears under the `911report` directory, we can use this command-line option to search for the occurances. 
```
qinken@Kens-MBP skill-demo1 % find technical/government/Alcohol_Problems > alcohol.txt
qinken@Kens-MBP skill-demo1 % grep -c "Session2" alcohol.txt
1
```
If we want to find how many file names in a specific directory contains the string `Session2`, we can combine `find` and `grep -c` to count the number of occurances that this string appears in the subdirectories of `Alcohol_Problems`. This is very useful to locate files and directories and count the file names or directories that contains that string.
* `grep -L`
```
qinken@Kens-MBP skill-demo1 % grep -L "Session*" */government/Alcohol_Problems/*.txt
technical/government/Alcohol_Problems/DraftRecom-PDF.txt
```
Instead of searching for matching lines, `grep -L` searches and output names of files that **does not** match the selected string. From this example, if we want to find files that does not contain "Session" in the directory of `Alcohol_Problems`, we can use `grep -L` to achieve this. This is useful when we want to filter out files that contain specific keywords.
```
qinken@Kens-MBP skill-demo1 % grep -L "terrorism" */911report/*.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-9.txt
technical/911report/preface.txt
```
In this example, if we want to find files in `911report` that does not contain the keyword "terrorism" in their contents, we could use `grep -L` to find those files. This is useful when we want to filter files to not contain sensitive words.
```
qinken@Kens-MBP skill-demo1 % grep -L "United States General Accouting Office" */government/Gen_Account_Office/*.txt
technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
technical/government/Gen_Account_Office/InternalControl_ai00021p.txt
technical/government/Gen_Account_Office/July11-2001_gg00172r.txt
technical/government/Gen_Account_Office/June30-2000_gg00135r.txt
technical/government/Gen_Account_Office/Letter_WalkerJan30-2001.txt
technical/government/Gen_Account_Office/Letter_Walkeraug17let.txt
technical/government/Gen_Account_Office/May1998_ai98068.txt
technical/government/Gen_Account_Office/Oct15-1999_gg00026t.txt
technical/government/Gen_Account_Office/Oct15-2001_d0224.txt
technical/government/Gen_Account_Office/Paper_Walker11-2002_acpro122.txt
technical/government/Gen_Account_Office/Sept14-2002_d011070.txt
technical/government/Gen_Account_Office/Sept27-2002_d02966.txt
technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
technical/government/Gen_Account_Office/Testimony_Jul15-2002_d02940t.txt
technical/government/Gen_Account_Office/Testimony_Jul17-2002_d02957t.txt
technical/government/Gen_Account_Office/Testimony_cg00010t.txt
technical/government/Gen_Account_Office/Testimony_d01609t.txt
technical/government/Gen_Account_Office/ai00134.txt
technical/government/Gen_Account_Office/ai2132.txt
technical/government/Gen_Account_Office/ai9868.txt
technical/government/Gen_Account_Office/d01121g.txt
technical/government/Gen_Account_Office/d01145g.txt
technical/government/Gen_Account_Office/d01186g.txt
technical/government/Gen_Account_Office/d01376g.txt
technical/government/Gen_Account_Office/d01591sp.txt
technical/government/Gen_Account_Office/d0269g.txt
technical/government/Gen_Account_Office/d02701.txt
technical/government/Gen_Account_Office/d03232sp.txt
technical/government/Gen_Account_Office/d03273g.txt
technical/government/Gen_Account_Office/d03419sp.txt
technical/government/Gen_Account_Office/ffm.txt
technical/government/Gen_Account_Office/gg96118.txt
technical/government/Gen_Account_Office/im814.txt
technical/government/Gen_Account_Office/og96009.txt
technical/government/Gen_Account_Office/og96011.txt
technical/government/Gen_Account_Office/og96012.txt
technical/government/Gen_Account_Office/og96014.txt
technical/government/Gen_Account_Office/og96015.txt
technical/government/Gen_Account_Office/og96020.txt
technical/government/Gen_Account_Office/og96021.txt
technical/government/Gen_Account_Office/og96022.txt
technical/government/Gen_Account_Office/og96023.txt
technical/government/Gen_Account_Office/og96026.txt
technical/government/Gen_Account_Office/og96027.txt
technical/government/Gen_Account_Office/og96028.txt
technical/government/Gen_Account_Office/og96031.txt
technical/government/Gen_Account_Office/og96032.txt
technical/government/Gen_Account_Office/og96033.txt
technical/government/Gen_Account_Office/og96034.txt
technical/government/Gen_Account_Office/og96036.txt
technical/government/Gen_Account_Office/og96037.txt
technical/government/Gen_Account_Office/og96038.txt
technical/government/Gen_Account_Office/og96040.txt
technical/government/Gen_Account_Office/og96041.txt
technical/government/Gen_Account_Office/og96042.txt
technical/government/Gen_Account_Office/og96043.txt
technical/government/Gen_Account_Office/og96045.txt
technical/government/Gen_Account_Office/og96047.txt
technical/government/Gen_Account_Office/og97001.txt
technical/government/Gen_Account_Office/og97002.txt
technical/government/Gen_Account_Office/og97003.txt
technical/government/Gen_Account_Office/og97011.txt
technical/government/Gen_Account_Office/og97019.txt
technical/government/Gen_Account_Office/og97020.txt
technical/government/Gen_Account_Office/og97023.txt
technical/government/Gen_Account_Office/og97028.txt
technical/government/Gen_Account_Office/og97032.txt
technical/government/Gen_Account_Office/og97038.txt
technical/government/Gen_Account_Office/og97039.txt
technical/government/Gen_Account_Office/og97041.txt
technical/government/Gen_Account_Office/og97043.txt
technical/government/Gen_Account_Office/og97045.txt
technical/government/Gen_Account_Office/og97046.txt
technical/government/Gen_Account_Office/og97050.txt
technical/government/Gen_Account_Office/og97051.txt
technical/government/Gen_Account_Office/og97052.txt
technical/government/Gen_Account_Office/og98018.txt
technical/government/Gen_Account_Office/og98019.txt
technical/government/Gen_Account_Office/og98022.txt
technical/government/Gen_Account_Office/og98024.txt
technical/government/Gen_Account_Office/og98026.txt
technical/government/Gen_Account_Office/og98029.txt
technical/government/Gen_Account_Office/og98030.txt
technical/government/Gen_Account_Office/og98032.txt
technical/government/Gen_Account_Office/og98040.txt
technical/government/Gen_Account_Office/og98041.txt
technical/government/Gen_Account_Office/og98044.txt
technical/government/Gen_Account_Office/og98045.txt
technical/government/Gen_Account_Office/og98046.txt
technical/government/Gen_Account_Office/og99036.txt
technical/government/Gen_Account_Office/pe1019.txt
```
This example shows `grep -L` on filtering out files that contains the title "United States General Accounting Office" and is useful in searching for unspecified files. Notice that `grep -L` command is different from `grep -l`, where one (`-L`) searches for names of files that **does not contain** the selected strings, and the other one (`-l`) only searches for names of files **contain** the selected strings. So we need to be aware of both upper case and lower case of the command-line options here.

* `grep -e`
```
qinken@Kens-MBP skill-demo1 % grep -e "Matt Myerhoff" -e "Kelly Greene" -e "Tina Spee" */*/*/*.txt
technical/government/Media/A_Perk_of_Age.txt:By Kelly Greene
technical/government/Media/Assuring_Underprivileged.txt:By Tina Spee
technical/government/Media/agency_expands.txt:By Matt Myerhoff
```
The `grep -e` commands here allow for multiple pattern searches with different strings. This is extremely useful when we want to find multiple files that matches with multiple strings. As shown above, if we want to find files that include these specific authors, we could use `-e` followed by the specified string multiple times to allow multiple matches.
```
qinken@Kens-MBP skill-demo1 % find technical/government/* > government.txt
qinken@Kens-MBP skill-demo1 % grep -e "Civil_Matters" -e "Progress_report" -e "Strategic_report" government.txt
technical/government/About_LSC/Progress_report.txt
technical/government/About_LSC/Strategic_report.txt
technical/government/Media/Civil_Matters.txt
```
Similarly, we can combine `grep -e` with `find` command to find multiple file names in the directory of `government` given specific strings. The example above showcases how we can find specific file names under certain directory using `grep -e`. This is useful to find matches for multiple file names.
```
qinken@Kens-MBP skill-demo1 % grep -e "Parkinson's disease" -e "Lichtenstein's art" */plos/*.txt 
technical/plos/journal.pbio.0020401.txt:        The consequence of Parkinson's disease (PD) is well described: a progressive movement
technical/plos/journal.pbio.0030051.txt:        stage(s) a new factor (e.g., nicotine, sleep deprivation, or Parkinson's disease) had its
technical/plos/journal.pbio.0030136.txt:        The core concept of Lichtenstein's art is the iconic—drastic simplification of line and
----------------------------------
qinken@Kens-MBP skill-demo1 % grep "Parkinson's disease\|Lichtenstein's art" */plos/*.txt 
technical/plos/journal.pbio.0020401.txt:        The consequence of Parkinson's disease (PD) is well described: a progressive movement
technical/plos/journal.pbio.0030051.txt:        stage(s) a new factor (e.g., nicotine, sleep deprivation, or Parkinson's disease) had its
technical/plos/journal.pbio.0030136.txt:        The core concept of Lichtenstein's art is the iconic—drastic simplification of line and
```
Notice that an alternative to the `grep -e` command that also allow to use multiple strings for searching is to simply use `grep` command with `\|` between the strings. Both methods produce the same outputs and are both very helpful when we want to search for lines that matches multiple patterns.