
###### This repository contains the notes from my unix server navigation learning.


# Commands

### Check current processes

#### `jps [ options ] [ hostid ]`


  `jps -l`
  * lists java processes with names

  `jps -l | sort -k2`
  * lists java processes with names, sorting alphabetically by the second column of data(app name)

`ps -o etime= -p "$$" `
* displays the time the process with PID "$$" has been running

`lsof -i :xxxx`
* displays who is using Port xxxx

`lsof | awk 'NR==1'`
* displayes what each column means on lsof

### Search

##### Grep
(Globally Search a Regular Expression and Print)

Search files for the occurrence of a string of characters that matches a specified pattern.

`grep "ND" file.log`
 * searches file.log for the string "ND" and prints that line to the console

`grep -A 10 -B 10 "URI" file.log`
* searches file.log for the string "URI" and prints that line as well as 10 lines above and below that line

==========================================================================================================================
##### Tail
Outputs the last part of a file.


`tail file.log.log`
* outputs the last 10 lines of file.log

`tail file.log -n 100`
* outputs the last 100 lines of file.log

`tail -f file.log`
* Outputs the last 10 lines of file.log, and monitors the file for updates, then it continues to output any new lines that are added

`tail -f file.log | grep keyword`
* Selectively monitor a log file in realtime
* tail monitors the log file, it then pipes the final ten lines and any new lines added to the grep utility, grep reads the output from tail and only displays the lines which contain the keyword

==========================================================================================================================
##### More
A filter for paging through text one screen at a time. It does not provide as many options or enhancements as less.

`more +3 file.log`
* displays the contents of file.log, beginning at line 3

`more +/"word" file.log`
* displays the contents of file, beginning at the first line containing the string "word"

**To exit a file reading mode, type `q`**

==========================================================================================================================
##### Less

==========================================================================================================================
##### VI  

`vi file.log`
* opens vi editor for file.log

`:$`
* goes to the bottom of the file

`vi fileThatDoesNotExist.extension`
* creates a file, to save exit with `:wq!`



