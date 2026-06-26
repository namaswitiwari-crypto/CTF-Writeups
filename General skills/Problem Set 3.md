\# General Skills - Problem Set 3



\## Challenge 1: Netcat Basics Again

\### Task

Connect to a host using Netcat.



\### Command

```bash

nc \[target\_host\_or\_IP] \[port\_number]   # generic usage

nc example.picoctf.net 12345           # actual command used

```

\###Explanation

* \*\*Netcat (nc)\*\* lets you connect to services running on specific ports.
* Here, I practiced connecting to a given host and port to retrieve the flag.



\## Challenge 2: Tab Tab Attack

\### Task

Unzip the provided archive and keep opening nested files until the flag is found.



\### Commands

```bash

unzip Addadshashanammu.zip                    #always remember Linux is case sensitive

cat Addadshashanammu.zip                      # scroll through content

grep --text pico Addadshashanammu.zip         # search directly

strings Addadshashanammu.zip | grep -i pico   # cleaner search

```



\### Explanation

* The challenge involved repeatedly opening files inside the archive until reaching the flag.
* \*\*grep\*\* and \*\*strings\*\* helped avoid scrolling through gibberish by directly searching for the flag pattern.
* This taught me how to handle large or noisy files efficiently.



\##Challenge 3: Python Script with Password

\###Task

Inspect the Python file to find the required password, then run it.



\### Commands

```bash

nano script.py        # open file to read password

python3 script.py     # execute with Python 3

```

###Explanation

* Opening the file with nano revealed the password prompt.
* After entering the correct password, the script printed the flag.
* This reinforced how to read and edit files before executing them.
* Since Python 2 is outdated, Python 3 is used to run the script.



\## Challenge 4: SSH Exploration

\###Task

Connect to a server via SSH and explore directories to collect flag parts.



\### Commands

```bash

ssh -p\[port number] \[username]@\[target-host]



then navigate through files with basic commands
ls -al          # to check all the files in current directory

cd \[directory]  # to change directory

cat \[file name] # to read the file

```



\### Explanation

* Using SSH, I logged into the server and navigated through /home and /root directories.
* Each directory contained a piece of the flag.
* By combining all parts, I obtained the complete flag.
* This challenge taught me how to explore remote systems securely and follow instructions to locate hidden files.



\### Takeaways

* Practiced connecting to services with \*\*Netcat\*\*.
* Learned to unzip and navigate nested files.
* Understood how to inspect Python scripts for hidden logic.
* Used \*\*SSH\*\* to explore directories and retrieve multiple flag parts.

