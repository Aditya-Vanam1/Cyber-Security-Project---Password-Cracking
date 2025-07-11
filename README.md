# Password-Cracking-Lab

  A practical lab to demonstrate password cracking using John the Ripper, Hashcat, and real-world wordlists to highlight the importance of strong passwords.

# 1.Creating Hashed Passwords
  echo -n "password123" | openssl passwd -6 -stdin
  echo -n "qwerty" | openssl passwd -6 -stdin

# 2.Saving Hashes to File
  nano hashes.txt

# 3.Unzip rockyou.txt Wordlist
  gunzip /usr/share/wordlists/rockyou.txt.gz

# 4.Cracking with John the Ripper
  john hashes.txt
  john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt
  john --show hashes.txt

# 5.Cracking with Hashcat (SHA-512 = 1800)
  hashcat -m 1800 -a 0 -o cracked.txt hashes.txt /usr/share/wordlists/rockyou.txt
  cat cracked.txt

# 6.Hash Type Identification
  hashid [your_hash]

# 7.Specify Format in John (optional)
  john --format=sha512crypt hashes.txt

# 8.Checking GPU Support in Hashcat
  hashcat -I
