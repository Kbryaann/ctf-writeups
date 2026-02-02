Bandit Level 5 -> 6

  Goal
  The password for the next level is stored in a file somewhere inside the inhere
  directory. The file has the following properties: it is human-readable, 1033 bytes in
   size, and not executable.

  Problem
  Using find, we located a file that matched the size and permission properties.
  However, when we used cat to view the file, it contained a very long, unreadable
  string of ASCII characters, not a clear password. This indicated the file was not
  plain text, even though it was identified as "ASCII text".

  Solution
   1. First, I used the find command to search the inhere directory and locate the file
      based on its specific size and executable properties.
   2. The file command confirmed we had the right file, but its content was not plain
      text.
   3. The key was to realize that the password might be a readable string embedded within
      a file that otherwise looks like data. The strings command is the perfect tool for
      this job, as it extracts readable character sequences from any file.
   4. Running the strings command on the file filtered out all the "junk" and printed the
      actual password.

  ---
  1. Find the file that matches the criteria

   1 # Search in the 'inhere' directory for a file that is 1033 bytes and not executable
   2 find ./inhere -type f -size 1033c ! -executable
  Output:
   1 ./inhere/maybehere07/.file2

  2. Analyze the file content to find the password

   1 # The 'cat' command showed unreadable text, so we use 'strings'
   2 # to extract only the readable parts from the file.
   3 strings ./inhere/maybehere07/.file2
  Output:

   1 <...some random characters...>
   2 <the actual password is printed here>
   3 <...more random characters...>

  Password for bandit6
  HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
