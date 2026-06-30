# Beginner Skills - Section 5

## Challenge 1: Enhance!
### Task
Download the image file and reconstruct the flag from the SVG content.

### Commands
```bash
cat drawing.flag.svg
```
### Explanation
- The flag characters were hidden inside <tspan> tags in the SVG file.
- By reconstructing the sequence (p → i → c → o → C → T → F{3nh4n...c3d_aab729dd}), the complete flag was revealed.
- This challenge taught me how flags can be embedded inside image metadata.

## Challenge 2: Big Zip
### Task
Unzip a huge archive and search for flag.txt.

### Commands
```bash
unzip big-zip-files.zip
grep -ri "pico" big-zip-files/   # recursive search, case-insensitive
```
### Explanation
- The archive contained many files, making manual search impractical.
- grep -r recursively searched all files for the flag string.
- This reinforced efficient searching in large datasets.

## Challenge 3: Vault Door Training
### Task
Read Java source code to reconstruct the flag.

### Steps
- Opened VaultDoorTraining.java with nano.
- Found the wrapper prefix (picoCTF{) and suffix (}).
- The checkPassword function revealed the secret token:
```Code
w4rm1ng_Up_w1tH_jAv4_000HPpgh7Ph
Reconstructed flag: picoCTF{w4rm1ng_Up_w1tH_jAv4_000HPpgh7Ph}
```

### Explanation
- Reading source code revealed the password logic.
- This challenge showed how to extract hidden flags from program logic.

## Challenge 4: Reverse Engineering (Keygen Trial)
### Task
Analyze keygenme-trial.py to reconstruct the flag.

### Commands
```bash
nano keygenme-trial.py
python3 -c 'import hashlib; print(hashlib.sha256(b"BENNETT").hexdigest())'
```
### Expanded Explanation
- The script defined a static template:
- picoCTF{1n_7h3_kk3y_of_} + xxxxxxxx + }.
- The dynamic part (xxxxxxxx) was derived from specific positions of the SHA‑256 hash of the username BENNETT.
- Running the one‑liner produced the full hash:
```code
ba6c084a4d888e1f7c3b0fc71d61c4625708bd915b5e0e60eb73e1667251b567
```
The code checked characters in this order:
- hexdigest()[4] → 0
- hexdigest()[5] → 8
- hexdigest()[3] → c
- hexdigest()[6] → 4
- hexdigest()[2] → 6
- hexdigest()[7] → a
- hexdigest()[1] → a
- hexdigest()[8] → 4

- Stringing them together gave the dynamic part: 08c46aa4.
- Stitching all parts together:
**picoCTF{1n_7h3_kk3y_of_08c46aa4}**

## Challenge 5: Buffer Overflow
### Task
Trigger a segmentation fault to print the flag.

### Commands
```bash
nc saturn.picoctf.net 52481

Input:
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
```
### Explanation
- The program allocated two buffers: buf1[100] and buf2[16].
- It used unsafe functions (gets, strcpy) that copied input without bounds checking.
- Overflowing buf2 caused a segmentation fault.
- A custom sigsegv_handler intercepted the crash and printed the flag.
-Final flag:
**picoCTF{ov3rfl0ws_ar3nt_that_bad_ef01832d}**

### Takeaways
- Learned how flags can be hidden in image metadata.  
- Practiced recursive searching in large archives.  
- Extracted flags by analyzing Java and Python source code.  
- Understood hashing and reverse engineering logic.  
- Reverse engineering often involves reading source code carefully and following how inputs are validated.  
- Hash functions like SHA‑256 are one‑way, but by tracing the program’s comparison logic,  can reconstruct the expected password.  
- Reinforced the importance of understanding hashing, indexing, and dynamic string construction.  
- Gained first exposure to buffer overflow vulnerabilities and exploitation.  
- Learned why unsafe functions (`gets`, `strcpy`) are dangerous and how buffer overflows can be exploited to trigger custom handlers.  
