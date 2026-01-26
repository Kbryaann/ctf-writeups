# Bandit Level 2 -> 3
    
    ## Goal
    Read the password from a file named `--spaces in this filename--`.
    
    ## Problem
    The filename contained both spaces and leading dashes, which caused errors.
      Using only quotes was not enough, as the leading dashes were still being
      interpreted as an option.
    
    ## Solution
   I learned to use the special `--` argument to tell the `cat` command to
      treat anything following it as a filename. I combined this with quotes to
      handle the spaces. This was the successful command:
  cat -- "--spaces in this filename--"
  
    ##Password for bandit3
    MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
