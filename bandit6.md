# Bandit Level 6 -> 7
    2 
    3 ## Goal
    4 The password for the next level is stored in a file somewhere on the server, not in the
      home directory. The file has the following properties:
    5 - Owned by user `bandit7`
    6 - Owned by group `bandit6`
    7 - 33 bytes in size
    8 
    9 ## Problem
   10 Since the file is not in the current directory, a system-wide search is necessary. A
      broad search like this will generate many "Permission denied" errors, which can hide the
      actual result.
   11 
   12 ## Solution
   13 1.  The `find` command is the correct tool to locate the file. The search must start from
      the root directory (`/`) to scan the entire filesystem.
   14 2.  The search was narrowed down using the `-user`, `-group`, and `-size` flags to match
      the exact properties of the target file.
   15 3.  To solve the issue of error messages cluttering the output, standard error was
      redirected to `/dev/null`. This special location discards any data written to it,
      effectively silencing the "Permission denied" errors.
   16 4.  Once the `find` command returned the single, correct file path, the `cat` command was
      used to read its content, revealing the password.
   17 
   18 ---
   19 ### 1. Find the file that matches the criteria
  Search the entire filesystem for a file owned by bandit7, in group bandit6,
  with a size of 33 bytes. Redirect errors to /dev/null.
  find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
   1 **Output:**
  /var/lib/dpkg/info/bandit7.password

   1 
   2 ### 2. Print the file content to get the password
  Read the content of the found file
  cat /var/lib/dpkg/info/bandit7.password
   1 **Output:**
  morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

   1 
   2 ## Password for bandit7
   3 morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
