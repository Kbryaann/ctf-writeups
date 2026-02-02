  1 # Bandit Level 4 -> 5
    2 
    3 ## Goal
    4 The password for the next level is stored in the only human-readable file
      within the `inhere` directory, which contains 10 possible files.
    5 
    6 ## Problem
    7 The `inhere` directory contains 10 files (`-file00` through `-file09`), and we
      need to find the one that is human-readable, as a simple `cat *` might corrupt
      the terminal if binary files are present. Also, filenames starting with a
      hyphen (`-`) can be misinterpreted as command options.
    8 
    9 ## Solution
   10 1.  First, I navigated into the `inhere` directory.
   11 2.  To identify the human-readable file among the 10, I used the `file`
      command. I used `--` before the wildcard `*` to ensure that filenames starting
      with a hyphen were treated as arguments, not options.
   12 3.  The output of `file -- *` revealed that `-file07` was an "ASCII text"
      file, indicating it was human-readable.
   13 4.  Finally, I used the `cat` command, again with `--` to handle the
      hyphenated filename, to display the contents of `-file07`, which contained the
      password.
  Navigate to the directory
  cd inhere

  Identify the type of each file in the directory
  The '--' ensures that filenames starting with '-' are treated as files, not 
  options.
  file -- *

  Output showed:
  -file00: data
  -file01: data
  -file02: data
  -file03: data
  -file04: data
  -file05: data
  -file06: data
  -file07: ASCII text  <-- This is the one!
  -file08: data
  -file09: data

  View the contents of the human-readable file
  cat -- '-file07'

   1 
   2 ## Password for bandit5
  4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

