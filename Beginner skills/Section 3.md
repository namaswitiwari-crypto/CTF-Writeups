# Beginner Skills - Section 3

## Challenge 1: Wave a Flag
### Task
Invoke help flags for a tool or binary. The flag was inside `warm`, but the file needed execution permissions first.

### Commands
```bash
chmod +x warm
./warm -h
```
### Explanation
- The hint suggested making the file executable **(chmod +x)** and then running it.

## Challenge 2: Tab, Tab, Attack
### Task
Unzip the provided archive and keep opening nested files until the flag is found.

### Commands
```bash
unzip Addadshashanammu.zip                    # Linux is case sensitive
cat Addadshashanammu.zip                      # scroll through content
grep --text pico Addadshashanammu.zip         # search directly
strings Addadshashanammu.zip | grep -i pico   # cleaner search
```

### Explanation
- The challenge involved repeatedly opening files inside the archive until reaching the flag.
- **grep** and **strings** helped avoid scrolling through gibberish by directly searching for the flag pattern.
- This taught me how to handle large or noisy files efficiently.

## Challenge 3: Inspect Website
### Task
Check the website at http://fickle-tempest.picoctf.net:59451/ for hidden flag parts.

### Steps
- Opened the site and inspected the source code.
- Found flag parts in **index.html**, **style.css**, and **script.js**.
- Refreshed the page to reveal hidden content in **index.html**.

### Explanation
- Inspecting source files revealed the flag in multiple parts.
- This challenge showed how flags can be hidden in web assets.

## Challenge 4: String It
### Task
Find the flag without running the file, using strings.

### Command
```bash
strings file | grep -i pico
```

### Explanation
- The **strings** command extracts readable **ASCII** text from binaries.
- Piping its output into **grep** -i allowed me to search for the flag signature directly.
- This method avoids executing potentially unsafe binaries.

## Challenge 5: First Grep
### Task
Search for a specific string inside a file using **grep**.

### Command
```bash
grep "pico" file.txt
```

### Explanation
- **grep** searches for patterns inside files.
- Here, I used it to locate the flag string directly instead of scrolling through the file.
- The -i option can be added to ignore case sensitivity.

## Challenge 6: Robots
### Task
Check the website at http://fickle-tempest.picoctf.net:56987 for hidden paths.

### Steps
- Navigated to url/robots.txt.
- Found a hint:
```Code
User-agent: *
Disallow: /cc6b1.html
```
- Edited the URL to http://fickle-tempest.picoctf.net:56987/cc6b1.html.
- The flag appeared on the page.

### Explanation
- robots.txt often contains disallowed paths.
- Accessing the hidden path revealed the flag.
- This challenge taught me how to use trial and error with URLs.

### Takeaways
- Learned to manage file permissions with **chmod**.
- Practiced searching inside noisy archives using **grep** and **strings**.
- Discovered how to inspect websites and hidden assets for flags.
- Reinforced basics of **grep** and **strings** for binary/text analysis.
- Understood how robots.txt can reveal hidden paths.