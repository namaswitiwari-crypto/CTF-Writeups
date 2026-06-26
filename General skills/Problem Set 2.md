# General Skills - Problem Set 2

## Challenge 1: Obedient Cat
### Task
Open the file and read the flag.

### Command
```bash
cat [file path]   # generic usage
cat flag.txt      # actual command used
```
#### Explanation
- The **cat** command displays the contents of a file.
- Here, simply opening the file revealed the flag.

## Challenge 2: Wave a Flag
### Task
Open the file, but the contents looked gibberish with the flag hidden inside.

### Commands
```bash
chmod +x warm
./warm -h
```
#### Explanation
- The hint suggested making the file executable **(chmod +x)** and then running it.

## Challenge 3: convertme.py
### Task
Execute the Python script to get the flag.

###Command
```bash
python3 [file path]    # generic usage
python3 convertme.py   # actual command used
```

#### Explanation
- Running the script with Python 3 executed the code and printed the flag.
- This taught me how to run Python files directly from the terminal.
- since python2 is out of date, so python3 interpreter is called. It reads, compiles and executes the code within the file.

## Challenge 4: What’s a Netcat?
### Task
Connect to a service using Netcat.

### Command
```bash
nc [target_ host_or_IP] [port_number]   # generic usage
nc fickle-tempest.picoctf.net 63441     # actual command used
```

#### Explanation
 
- **Netcat (nc)** is used to connect to services running on specific ports.
- Here, I learned the format of connecting with Netcat: specifying the port and host.
- This challenge reinforced how Netcat is a versatile tool for interacting with remote services.
---

###Takeaways
- Practiced reading files with cat.
- Learned to search inside files with grep.
- Understood how to make files executable with chmod +x.
- Ran Python scripts using python3.
- Gained confidence using Netcat to connect to services.

