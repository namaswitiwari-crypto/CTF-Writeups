# Beginner Skills - Section 2 (CyberChef)

## Challenge 1: ROT13
### Task
Use ROT13 to encode/decode the flag in the file.

### Tool Used
CyberChef (ROT13 operation)

### Explanation
- ROT13 shifts each letter by 13 places in the alphabet.  
- In CyberChef, selecting the ROT13 operation and pasting the flag text revealed the decoded flag.


## Challenge 2: Hex to Decimal
### Task
Convert `0x3D` (base 16) into decimal (base 10).

### Tool Used
CyberChef (From Hex → To Decimal)

### Explanation
- `0x3D` is hexadecimal notation.  
- CyberChef converted it directly to decimal.  
- The result was `61`.


## Challenge 3: Decimal to Binary
### Task
Convert the number `42` (base 10) into binary (base 2).

### Tool Used
CyberChef (From Decimal → To Binary)

### Explanation
- CyberChef converted `42` into binary.  
- The result was `101010`.


## Challenge 4: Base64 Decode
### Task
Decode the string `bDNhcm5fdGgzX3IwcDM1`.

### Command
```bash
echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d
```
### Explanation
- The string was Base64 encoded.
- Using base64 -d decoded it into readable ASCII text.
- The decoded flag was revealed.

### Takeaways
- Practiced encoding/decoding with ROT13 in CyberChef.
- Converted numbers between hexadecimal, decimal, and binary using CyberChef.
- Learned how to decode Base64 strings directly in the terminal.
- Built confidence in combining CyberChef with command‑line tools.
