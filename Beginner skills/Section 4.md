# Beginner Skills - Section 4

## Challenge 1: Python Wrangling
### Task
Run `ende.py` using `password.txt` to decrypt `flag.txt.en`.

### Commands
```bash
nano ende.py              # check script format
cat password.txt          # read the password
python3 ende.py -d flag.txt.en
```
### Explanation
- Opening ende.py showed the format for decryption.
- The password was stored in password.txt.
- Running the script with -d decrypted flag.txt.en and revealed the flag.
- This reinforced how Python scripts can be used like executables.

## Challenge 2: PW1
### Task
Run script.py and enter the correct password.

### Commands
```bash
nano script.py            # open file to read password
python3 script.py         # execute with Python 3
```

### Explanation
- Inside the script, the condition if(user_pw == "691d"): revealed the password.
- Entering 691d when prompted displayed the flag.
- This showed how reading code can reveal hidden logic.
- Python 3 was used since Python 2 is outdated.

## Challenge 3: PW2
### Task
Find the password hidden in character codes.

### Commands
```bash
nano level2.py
python3 -c 'print(chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65))'
python3 level2.py
```
### Explanation
- The script contained if(user_pw == chr(0x33)+chr(0x39)+chr(0x63)+chr(0x65)):.
- Running the one‑liner revealed the password 39ce.
- Entering 39ce when executing level2.py displayed the flag.
- This taught me how to decode ASCII values in Python.

## Challenge 4: PW3
### Task
Crack the password using hashing.

### Commands
```bash
nano level3.py                                                  # to open and check passwords

python3 -c '                                                    # to find the correct password
import hashlib
target = open("level3.hash.bin", "rb").read()
for pw in ["6997","3ac8","f0ac","4b17","ec27","4e66","865e"]:
    if hashlib.md5(pw.encode()).digest() == target:
        print(f"FOUND MATCH: {pw}")
'

python3 level3.py                                               # to execute the file
```
### Explanation
- The script listed seven possible passwords.
- A Python snippet tested each against the stored hash.
- The correct password was identified and used to reveal the flag.

Key concepts:
- rb mode reads raw binary data.
- pw.encode() converts text to bytes.
- hashlib.md5().digest() produces raw hash bytes.
- This challenge introduced cryptographic hashing and password verification.

## Challenge 5: PW4
### Task
Crack the password from a list of 100 candidates.

Option A: External Script
```bash
nano level4.py
python3 -c '
import hashlib
target = open("level4.hash.bin", "rb").read()
for pw in [ <100_passwords_here> ]:
    if hashlib.md5(pw.encode()).digest() == target:
        print(f"FOUND MATCH: {pw}")
'
```

Option B: Edit Script {add this at the end of the file}
```python
for pw in pos_pw_list:
    if hash_pw(pw) == correct_pw_hash:
        print(f"The correct password is: {pw}")
```
### Explanation
- Either brute‑force externally or edit the script to loop through the candidate list.
- Running level4.py revealed the correct password and flag.
- This reinforced how to automate password testing.

## Challenge 6: PW5
### Task
Use a dictionary file to crack the password.

### Commands
```bash 
head dictionary.txt        # preview candidate passwords
nano level5.py             # edit script
```
```Added Code
python
with open("dictionary.txt", "r") as f:
    for line in f:
        pw = line.strip()
        if hash_pw(pw) == correct_pw_hash:
            print(f"FOUND PASSWORD: {pw}")
            break
```
```bash 
python3 level5.py         # to execute the file
```

### Explanation
- The script was modified to read from dictionary.txt.
- Each password was hashed and compared against the stored hash.
- The correct password was found and used to decrypt the flag.
- This demonstrated dictionary attacks and script modification.

### Takeaways
- Learned how to run and edit Python scripts.
- Practiced extracting passwords hidden in code and ASCII values.
- Understood hashing concepts (encode, digest, rb).
- Automated brute‑force and dictionary attacks using Python.
- Built confidence in combining code analysis with cryptography.

