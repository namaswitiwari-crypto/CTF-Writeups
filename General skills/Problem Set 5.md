# General Skills - Problem Set 5

## Challenge 1: Static Ain’t Always Noise
### Task
Analyze the binary file `static` using the provided bash script.

### Commands
```bash
chmod +x ltdis.sh              # give execution permissions to the script
./ltdis.sh static              # run the script with the binary as argument
cat static.ltdis.strings.txt | grep pico   # search for the flag inside generated strings
```
### Explanation
- By default, **downloaded scripts don’t have execution permissions, so chmod +x is needed**.
- Running ltdis.sh disassembles the binary and generates a .strings.txt file.
- Since flags are stored as ASCII text inside binaries, searching with grep revealed the flag.

## Challenge 2: Strings Usage
### Task
Find the flag without running the file, using strings.

### Command
```bash
strings file | grep -i pico
```

### Explanation
- The **strings** command extracts readable ASCII text from binaries.
- Piping its output into **grep -i** allowed me to search for the flag signature directly.
- This method avoids executing potentially unsafe binaries.

## Challenge 3: Process Data with Netcat
### Task
Capture output from a running program and search for the flag.

### Commands
```bash
nc fickle-tempest.picoctf.net 51625

Hint suggested using a pipe:
nc fickle-tempest.picoctf.net 51625 | grep "pico"
```

### Explanation
- **Netcat (nc)** connected me to the remote service.
- Instead of manually scanning the output, I piped it into **grep** to filter for the flag.
- This challenge taught me how to handle process data streams efficiently.


## Takeaways
- Learned to analyze binaries using helper scripts.
- Practiced extracting readable text with strings.
- Understood how to filter live process output using pipes.
- Gained confidence combining commands for secure and efficient flag discovery.