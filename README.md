# WiseGuy-TryHackMe-Writeup
Target Machine IP: 10.65.171.229
I uploaded the decryption Python file, which we will use to decrypt the encoded text into the FLAG.

Note: Use Terminator Terminal and open two terminal instances.

# Task
The challenge is a cryptographic task that needs to be solved. We are provided with the source and the open port 1337 of the machine that sets the task. 
As we know port no 1337, so we run a detailed NMAP Scan

    nmap -p 1337 --script=banner 10.65.171.229

This Command will fetch any details available behind the port

![Screenshot 2025-12-12 012434](https://github.com/user-attachments/assets/6fe14947-364d-4bf0-9c1e-a301ffc844c4)

However, the flag is still encoded in XOR ASCII text, so open the terminator terminal and try to connect to the Target Machine
  
    nc 10.65.171.229 1337 
    
![1](https://github.com/user-attachments/assets/ac64c327-5efc-41ae-992a-17b2a6ca9272)

Now We Get an XOR-coded text 
# Copy the code and use the decryption_script.py to decrypt the 1st flag
    python3 decryption_script.py <paste the encoded numbers you get when connecting to the server>
![2](https://github.com/user-attachments/assets/5c058a32-387c-43a0-af63-475db9b81389)
So we get our first flag and the encryption key, which will get us our 2nd flag 

Now, enter the encrypted key into the terminal where netcat is running, and here you go, you get the 2nd flag.
