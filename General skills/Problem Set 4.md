# General Skills - Problem Set 4

## Challenge 1: First Grep
### Task
Search for a specific string inside a file using `grep`.

### Command
```bash
grep "pico" file.txt      # actual command used
```
### Explanation
- **grep** searches for patterns inside files.
- Here, I used it to locate the flag string directly instead of scrolling through the file.
- The -i option can be added to ignore case sensitivity.

## Challenge 2: First Find
### Task
Unzip the file and locate uber-secret.txt.

### Commands
```bash
unzip files.zip
find . -name "uber-secret.txt"
cat ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
```

### Explanation
- After unzipping, I used find to search for the file by name.
- Once located, opening it with cat revealed the flag.
- This taught me how to quickly locate files in nested directories.

## Challenge 3: Big Zip Again
### Task
Unzip a huge archive and use grep to find flag.txt.

### Commands
```bash
unzip big-zip-files.zip
grep -ri "pico" big-zip-files.zip   # -r for recursive search, -i ignores case
```

### Explanation
- The archive contained many files, so manually searching wasn’t practical.
- Using grep -r allowed me to recursively search through all files for the flag.
- This challenge showed how to combine unzipping with efficient searching.

### Takeaways
- Practiced searching text with grep.
- Learned to locate files using find.
- Understood how to handle large archives with recursive search.
- Gained confidence in combining commands to solve complex tasks.
