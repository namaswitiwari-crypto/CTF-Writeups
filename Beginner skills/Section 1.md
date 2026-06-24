# Beginner Skills - Section 1 (Sanity)

## Challenge 1: Obedient Cat
### Task
Open the file and read the flag.

### Command
```bash
cat flag.txt
```
### Explanation
- The **cat** command displays the contents of a file.
- Opening flag.txt revealed the flag directly.

## Challenge 2: Super SSH
### Task
Connect to a remote server using SSH.

### Command
```bash
ssh -p [port number] [username]@[target host]   # general usage 
ssh -p 57481 ctf-player@titan.picoctf.net       # actual usage
```

### Explanation
- **SSH (Secure Shell)** is used to log into remote servers securely.
- The -p option specifies the port number.
- After connecting as ctf-player and entering the password, the flag was revealed.

## Challenge 3: What’s a Netcat?
### Task
Connect to a service using Netcat.

### Command
```bash
nc [target host] [port number]        # general usage
nc fickle-tempest.picoctf.net 64530   # actual usage 
```

### Explanation
- **Netcat (nc)** connects to services running on specific ports.
- Connecting to the given host and port displayed the flag.

### Takeaways
- Practiced reading files with cat.
- Learned how to connect to remote servers using SSH.
- Gained confidence using Netcat to connect to services.