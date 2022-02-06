# Overview
Tested procedure for recovery of GPG keys.  This is for GnuPG version 2.
# Procedure
1. Preparation

    Remove all existing keyrings

    ```
    rm -rf ~/.gnupg
    ```
    
2. Retrieve private key from secret place, copy contents into a new file `~/restore-key.asc`
   
3. Import the keys

    Use GnuPG version 2
    
    ```
    gpg --import ~/restore-key.asc
    ```
    
    Make sure the keys are installed
    
    ```
    gpg --list-keys
    gpg --list-secret-keys
    ```
     
4. Delete the key that was imported

    ```
     rm -rf ~/restore-key.asc
     ```
5.  Test the recovery
    1.  Clone the blackbox demo
        
        ```
        cd /tmp && rm -rf blackbox-demo \
        && git clone https://github.com/deepeeess/blackbox-demo.git && cd blackbox-demo
        ```
    2. Test the ability to decrypt the file
        
        ```
        blackbox_decrypt_all_files
        blackbox_shred_all_files
        ```
    
# Reference

[blackbox-demo](https://github.com/dsulli99/blackbox-demo)
