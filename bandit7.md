Nice job! Here is the Markdown write-up for Level 7.

    1 # Bandit Level 7 -> 8
    2 
    3 ## Goal
    4 The password for the next level is located in the file `data.txt`, on the same line as
      the word "millionth".
    5 
    6 ## Problem
    7 The `data.txt` file contains a large volume of text, making it impractical to find the
      specific word and its corresponding password by manual inspection.
    8 
    9 ## Solution
   10 1.  The `grep` command is the most efficient tool for this problem. It is designed to
      search for specific patterns within files.
   11 2.  By running `grep` with the pattern "millionth" on the `data.txt` file, the command
      instantly filters all the lines and displays only the one containing the search term.
   12 3.  The password was the string of characters located next to the word "millionth" on the
      output line.
   13 
   14 ---
   15 ### 1. Search for the line containing the keyword
  Use grep to find the line with the word "millionth" in data.txt
  grep "millionth" data.txt
   1 **Output:**
  millionth dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
   1 
   2 ## Password for bandit8
   3 dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
