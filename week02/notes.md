Ques1. What did `pwd` print?
Ans1. pwd shows the full path of the folder you're currently "in" in the terminal.
      Printed:

&#x20;     Path

&#x20;     ----

&#x20;     C:\\WINDOWS\\system32







Ques2. What did `ls -Force` show that plain `ls` did not?
Ans2.  ls -Force reveals hidden files and folders — these are typically files/folders files marked with the "hidden" attribute on Windows. Plain ls skips these by default; ls -Force shows everything, including hidden items.




Ques3. Pick one line from `ls`. What do you think the `Mode` column means?
Ans3.  Mode                 LastWriteTime         Length Name

&#x20;      ----                 -------------         ------ ----
       d-----        01-04-2024     13:36                0409


       The Mode column shows the file type and permissions.It usually looks something like d----- or -a----
       The first character tells you the type: d = directory (folder), - = regular file, l = symbolic link

&#x20;      The remaining letters indicate attributes like a (archive), r (read-only), h (hidden), s (system)





Ques4. Why does that work from where you are standing? Which kind of path is `coding-cafe\\week02`? Absolute or Relative?

Ans4.  We're standing in our home folder because we just ran cd \~. The command ls coding-cafe\\week02 works without using cd because ls can accept a path as an argument, it doesn't require us to actually move into a folder first. Since coding-cafe exists directly inside our home folder, the terminal can find coding-cafe\\week02 by looking relative to where we currently are (home), listing its contents without ever changing our actual location.
It's a relative path, it's written relative to our current working directory (home), not from the root of the drive.





Ques5. `mv` did two different jobs above. What were they?

Ans5. Job 1 — Moving/relocating a file:



mv README-backup.md week01\\



Here, the destination (week01\\) is a folder, not a filename. So mv moved README-backup.md from coding-cafe into the week01 subfolder, keeping the same filename. The file's location changed, but not its name.

Job 2 — Renaming a file:



mv README-backup.md old-readme.md



Here, you were already inside week01, and the destination (old-readme.md) is a new filename, not a folder. So mv renamed the file in place — same location, new name.



Ques6. How many folders are on your `PATH`?

Ans6.  No. of folders: 9
C:\\WINDOWS\\system32

C:\\WINDOWS

C:\\WINDOWS\\System32\\Wbem

C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\

C:\\WINDOWS\\System32\\OpenSSH\\

C:\\Program Files\\dotnet\\

C:\\Users\\Dhriti Duggal\\AppData\\Local\\Microsoft\\WindowsApps

C:\\Users\\Dhriti Duggal\\AppData\\Local\\Programs\\Microsoft VS Code\\bin

C:\\Users\\Dhriti Duggal\\Downloads\\gcc-16.1.0-gdb-17.2.90.20260510-binutils-2.46.0-mingw-w64-v14.0.0-ucrt\\bin

Ques7. \*\*Write down exactly where your `python` lives\*\* — the `Source` column. You will need this again in a minute.
Ans7.  CommandType     Name                                               Version    Source

&#x20;      -----------     ----                                               -------    ------

&#x20;      Application     python.exe                                         0.0.0.0    C:\\Users\\Dhriti Duggal\\AppData\\Local\\M...

Ques8. Compare your answer to 7 with the person next to you. Are they the same? If not, why might that be?
Ans8.  No, the source is not the same. Different usernames/user folders (like C:\\Users\\YourName\\...) will naturally show different paths even with the same setup, since installs are often user-specific.

Ques9. What exactly did the shell say? Explain the error in your own words, using the word \*\*PATH\*\*.
Ans9.  pyton : The term 'pyton' is not recognized as the name of a cmdlet, function, script file, or operable program. Check

the spelling of the name, or if a path was included, verify that the path is correct and try again.

At line:1 char:1

\+ pyton

\+ \~\~\~\~\~

&#x20;   + CategoryInfo          : ObjectNotFound: (pyton:String) \[], CommandNotFoundException

&#x20;   + FullyQualifiedErrorId : CommandNotFoundException

When I typed pyton, PowerShell tried to find a program with that exact name by searching through every folder listed in my PATH environment variable, one folder at a time. Since I misspelled python as pyton, there was no file called pyton.exe (or similar) in any of those folders, only python.exe exists there, under the correct spelling.

Ques10. `.venv` did not appear with plain `ls`. Why not? 
Ans10.  .venv didn't show up with plain ls because folders (and files) that start with a dot (.) are treated as hidden by convention in most shells, including PowerShell when it's mimicking Unix-style behavior.

Ques11. What changed about your prompt?
Ans11.  After running .venv\\Scripts\\Activate.ps1 , `(.venv)` can be seen at the beginning of the prompt.



Ques12. Compare this with what you wrote down for question 7. Is it the same path? If not, what does that tell

&#x20;   you about what `Activate.ps1` actually did to your `PATH`?
Ans12.  CommandType     Name                                               Version    Source

&#x20;       -----------     ----                                               -------    ------

&#x20;       Application     python.exe                                         3.14.71... C:\\WINDOWS\\system32\\coding-cafe\\.venv\\...

Running Activate.ps1 added my virtual environment's script folder (coding-cafe\\.venv\\Scripts\\) to the front of your PATH. 

Ques13. What is in the second list that was not in the first?
Ans13.  First list had only:

Package Version

\------- -------

pip     26.2.1

Second list also had:

Package            Version

\------------------ ---------

certifi            2026.7.22

charset-normalizer 3.5.1

idna               3.19

pip                26.2.1

requests           2.34.2

urllib3            2.7.0



Ques14. Where does `python` point now?
Ans14.  Python points to the Windows Store stub, same as ques7 — C:\\Users\\Dhriti Duggal\\AppData\\Local\\Microsoft\\WindowsApps\\python.exe



Ques15. Find what the `-Recurse` flag does. Write it in your own words.

Ans15.  It digs into every subfolder, and every subfolder inside those, and so on — listing everything at every level, not just the surface.



Ques16. What is the difference between what Ctrl + C and Ctrl + Z did?

Ans16.  Ctrl + C = interrupts the current action but keeps the program (Python) running.

&#x20;       Ctrl + Z followed by Enter = tells the program there's no more input, causing it to exit completely and return you to PowerShell.

