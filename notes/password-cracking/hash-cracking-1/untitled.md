# Hashcat

* You can integrate hashcat with graphics card.

### Step 1\) Determine the hash type

* `./hashid.py`
  * _paste\_you\_hash_
* `hashcat example-hashes | less`
  * This will print list of all possible hash type
  * Now compare this list with our target hash find out earlier using hashid
    * There may be more than one hash algorithms with same hash key length, say for key length of 384 we have three hash types "SHA2-384" vs "SHA3-384" vs "Keccak-384"
    * compare length of hash and other parameters
    * we need to perform hashcat for all possible identified hash type.
    * find the "MODE" number of each matched hash type. Say MODE=10800

### Step 2\) Crack all possible hash types identified in step 1.

* \(SHA2-384\) `hashcat -m 10800 hashes/sha384 /usr/share/seclists/rockyou.txt`
* \(SHA3-384\) `hashcat -m 17500 hashes/sha384 /usr/share/seclists/rockyou.txt`
* \(Keccak-384\) `hashcat -m 17900 hashes/sha384 /usr/share/seclists/rockyou.txt`

### Step 3\) Advance Hash cracking

* \(Keccak-384\) `hashcat -m 17900 hashes/sha384 /usr/share/seclists/rockyou.txt -r rules/InsidePro-PasswordsPro.rule`

### Step 4\) Print the cracked passwords

* \(Keccak-384\) `hashcat -m 17900 hashes/sha384 --show`

