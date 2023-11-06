# Lab Report 3 - Bugs and Commands
## Part 1 - Bugs
Choose one of the bugs from week 4's lab
### Chosen Bug: The reversedInPlace method found in ArrayExamples that fail to correctly change the input array to be in reversed order.
- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
<br>JUnit test that has a failure-inducting input:
``` java
  @Test
  public void testReverseInPlace2(){
    int[] input1 = { 2, 4, 6};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 6, 4, 2}, input1);
  }
```
- An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
<br>JUnit test that does not induce a failure: 
``` java
	@Test 
	public void testReverseInPlace1() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```
### The symptom:
![Image](LR3symptom.png)
- The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue:
``` java
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
``` java
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < (arr.length/2); i += 1) {
      int tempInt = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length -i - 1] = tempInt;
    }
  }
```
This fix has multiple parts that ultimately all together address the issue. Firstly, since we are simply swapping the elements in the input array, there is no need to recurse through the entire array, as this will just result with the exact same input array. Alternatively, we only recurse through half of the input array, swapping every element just once. Secondly, it is important that initialize a temporary integer that can keep track of the number we are kicking, or swapping out. This ensures that the value is not 'lost'. Lastly it is important that we complete the swap by setting our tempInt into its new position which is where we got our previous number.
## Part 2 - Researching Commands
### Chosen Command: find
The find command is used to search for files and directories within a specified directory hierarchy
__Command-Line Option 1: "-type"__
<br>1. The first example for the 'type' option is using 'f' which searches for regular files. The path given goes to the 911report directory so it is only searching in that diretory. This is useful because sometimes directories will have both files and directories which can make certain actions difficult as you cannot treat files and directories the same. This way, you can section, or specifically refer to the files in the any given directory.
<br>Command:
```
$ find /Users/ycardenas/docsearch/technical/911report -type f
```
<br>Output:
```
/Users/ycardenas/docsearch/technical/911report/chapter-13.4.txt
/Users/ycardenas/docsearch/technical/911report/chapter-13.5.txt
/Users/ycardenas/docsearch/technical/911report/chapter-13.1.txt
/Users/ycardenas/docsearch/technical/911report/chapter-13.2.txt
/Users/ycardenas/docsearch/technical/911report/chapter-13.3.txt
/Users/ycardenas/docsearch/technical/911report/chapter-3.txt
/Users/ycardenas/docsearch/technical/911report/chapter-2.txt
/Users/ycardenas/docsearch/technical/911report/chapter-1.txt
/Users/ycardenas/docsearch/technical/911report/chapter-5.txt
/Users/ycardenas/docsearch/technical/911report/chapter-6.txt
/Users/ycardenas/docsearch/technical/911report/chapter-7.txt
/Users/ycardenas/docsearch/technical/911report/chapter-9.txt
/Users/ycardenas/docsearch/technical/911report/chapter-8.txt
/Users/ycardenas/docsearch/technical/911report/preface.txt
/Users/ycardenas/docsearch/technical/911report/chapter-12.txt
/Users/ycardenas/docsearch/technical/911report/chapter-10.txt
/Users/ycardenas/docsearch/technical/911report/chapter-11.txt
```
<br>2. The second example for the 'type' option is using 'd' which searches for regular diretories in the given path. The path given goes to the techinical directory so it is only searching in that diretory and its subdirectories. This is useful because sometimes directories will have both files and directories which can make certain actions difficult as you cannot treat files and directories the same. This way, you can section, or specifically refer to the directories in the any given directory and its subdirectories.
<br>Command:
```
$ find /Users/ycardenas/docsearch/technical -type d  
```
<br>Output:
```
/Users/ycardenas/docsearch/technical
/Users/ycardenas/docsearch/technical/government
/Users/ycardenas/docsearch/technical/government/About_LSC
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen
/Users/ycardenas/docsearch/technical/government/Alcohol_Problems
/Users/ycardenas/docsearch/technical/government/Gen_Account_Office
/Users/ycardenas/docsearch/technical/government/Post_Rate_Comm
/Users/ycardenas/docsearch/technical/government/Media
/Users/ycardenas/docsearch/technical/plos
/Users/ycardenas/docsearch/technical/biomed
/Users/ycardenas/docsearch/technical/911report
```
<br> __Command-Line Option 2:"-print"__
<br>1. The first example for the 'print' option is using a path that leads to the 911report directory in technical. This command prints the paths for every files and/or directory in the given path, including the origical path. This is useful because you can check the contents of something and also see how to refernece it.
<br>Command:
```
$ find /Users/ycardenas/docsearch/technical/911report -print
```
<br>Output:
```
/Users/ycardenas/docsearch/technical/911report
/Users/ycardenas/docsearch/technical/911report/chapter-13.4.txt
/Users/ycardenas/docsearch/technical/911report/chapter-13.5.txt
/Users/ycardenas/docsearch/technical/911report/chapter-13.1.txt
/Users/ycardenas/docsearch/technical/911report/chapter-13.2.txt
/Users/ycardenas/docsearch/technical/911report/chapter-13.3.txt
/Users/ycardenas/docsearch/technical/911report/chapter-3.txt
/Users/ycardenas/docsearch/technical/911report/chapter-2.txt
/Users/ycardenas/docsearch/technical/911report/chapter-1.txt
/Users/ycardenas/docsearch/technical/911report/chapter-5.txt
/Users/ycardenas/docsearch/technical/911report/chapter-6.txt
/Users/ycardenas/docsearch/technical/911report/chapter-7.txt
/Users/ycardenas/docsearch/technical/911report/chapter-9.txt
/Users/ycardenas/docsearch/technical/911report/chapter-8.txt
/Users/ycardenas/docsearch/technical/911report/preface.txt
/Users/ycardenas/docsearch/technical/911report/chapter-12.txt
/Users/ycardenas/docsearch/technical/911report/chapter-10.txt
/Users/ycardenas/docsearch/technical/911report/chapter-11.txt
```
<br>2. The second example for the '-print' option is using a path that leads to the Env_Prot_Agen directory in /technical/government. This command prints the paths for every files and/or directory in the given path, including the origical path. This is useful because you can check the contents of something and also see how to refernece it.
<br>Command:
```
$ find /Users/ycardenas/docsearch/technical/government/Env_Prot_Agen -print
```
<br>Output:
```
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/multi102902.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/section-by-section_summary.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/jeffordslieberm.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/final.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/ctf7-10.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/ctf1-6.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/ro_clear_skies_book.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/ctm4-10.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/1-3_meth_901.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/atx1-6.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/tech_sectiong.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/bill.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/nov1.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/tech_adden.txt
```
<br> __Command-Line Option 3:"-name"__
<br>1. The first example for the 'name' option is using the pattern '*.txt' which looks for all the files in the given path and inculde '.txt' in their name. This is useful because it allows you to single out specific text files, or categorize certain names of files.
<br>Command:
```
$ find /Users/ycardenas/docsearch/technical/government/Env_Prot_Agen -name "*.txt"
```
<br>Output:
```
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/multi102902.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/section-by-section_summary.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/jeffordslieberm.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/final.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/ctf7-10.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/ctf1-6.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/ro_clear_skies_book.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/ctm4-10.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/1-3_meth_901.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/atx1-6.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/tech_sectiong.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/bill.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/nov1.txt
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen/tech_adden.txt
```
<br>2. The second example for the 'name' option is using the name 'chapter-1.txt' which looks for all the files in the given path and inculde 'chapter-1.txt' in their name. This is useful because it allows you to find the path of a specific file you might be looking for.
<br>Command:
```
$ find /Users/ycardenas/docsearch/technical -name "chapter-1.txt"
```
<br>Output:
```
/Users/ycardenas/docsearch/technical/911report/chapter-1.txt
```
<br> __Command-Line Option 4:"-not"__
<br>1. The first example for the '-not' option is the name 'biomed'. In this case the command finds all the directories that do NOT have 'biomed' in its name. This is useful because sometimes we want to exclude a specific folder.
<br>Command:
```
$ find /Users/ycardenas/docsearch/technical -type d -not -name "biomed"
```
<br>Output:
```
/Users/ycardenas/docsearch/technical
/Users/ycardenas/docsearch/technical/government
/Users/ycardenas/docsearch/technical/government/About_LSC
/Users/ycardenas/docsearch/technical/government/Env_Prot_Agen
/Users/ycardenas/docsearch/technical/government/Alcohol_Problems
/Users/ycardenas/docsearch/technical/government/Gen_Account_Office
/Users/ycardenas/docsearch/technical/government/Post_Rate_Comm
/Users/ycardenas/docsearch/technical/government/Media
/Users/ycardenas/docsearch/technical/plos
/Users/ycardenas/docsearch/technical/911report
```
<br>2. The second example for the '-not' option is the name 'biomed'. In this case the command is references all the directories and subdirectories in the current working diretory. The command finds all the directories that do NOT have 'biomed' in its name. This is useful because sometimes we want to exclude a specific folder.
<br>Command:
```
$ find . -type d -not -name "biomed" 
```
<br>Output:
```
.
./government
./government/About_LSC
./government/Env_Prot_Agen
./government/Alcohol_Problems
./government/Gen_Account_Office
./government/Post_Rate_Comm
./government/Media
./plos
./911report
```
I find out about all of these examples through ChatGPT. Here is the prompts I used, "find command line options for the less command", "now for the find command", "now for the grep command".
