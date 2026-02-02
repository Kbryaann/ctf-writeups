# Bandit Level 3 -> 4
    
    ## Goal
    The goal is to Find the password for the next level,which is hidden in a file within the inhere directory
    
    ## Problem
    When listing the contents of the `inhere` directory using `ls -la`, it appeared to be empty, suggesting the file was hidden or had an unusual
      name.
    
    ## Solution
   I used the find command to be able to find the ...Hiding-From-You file then cat command to view its contents which contained the password  
   
    Navigate to the directory
  cd inhere

  Use find to locate the hidden file.
  The '.' means search in the current directory.
  '-type f' specifies we are looking for a file.
  '-name "Hiding-From-You"' searches for files whose name contains "Hiding-From-You".
  find . -type f -name "Hiding-From-You"

  Example output: ./._.Hiding-From-You

  Use cat to view the contents of the found file
  cat ./._.Hiding-From-You

  
    ##Password for bandit4
    2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

   
