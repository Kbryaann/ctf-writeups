 Bandit Level 0 -> 1
   
 ## Goal
The goal of this level is to find the password for the next level, which is
     stored somewhere on the server.
 
 # Solution
 I connected to the server using the provided credentials for `bandit0`.
      ssh bandit0@bandit.labs.overthewire.org -p 2220
 I listed the files in the home directory using the `ls` command.
      bandit0@bandit:~$ ls
      readme

  I found a file named `readme` and used the `cat` command to read its
     content.
      cat readme
  The output contained the password for the next level.
  
   ## Password for bandit1
   ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

