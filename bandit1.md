# Bandit Level 1 -> 2
    
   ## Goal
    The password for the next level is in a file named `-`.
    
   ## Problem
    The `cat -` command did not work as expected. It was waiting for standard
      input instead of reading the file.
    
   ## Solution
   I learned that a single dash (`-`) is often a special character for
      standard input. To read the file, I had to provide a path to it, so the
      command would treat it as a literal file.
  cat ./-
  
   ## Password for bandit2
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
