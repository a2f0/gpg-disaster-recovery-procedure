# Overview
Tested procedure for recovery of GPG keys.  This is for GnuPG version 2.
# Procedure
1. Preparation

    Remove all existing keyrings

    ```
    rm -rf ~/.gnupg
    ```
    
2. Retrieve keys from secret place, create two files
    1. ~/gnupg-dansullivan-public.txt
    2. ~/gnupg-dansullivan-private.txt
3. Import the keys

    Use gpg
    
    ```
    gpg --import ~/gnupg-dansullivan-public.txt
    gpg --import ~/gnupg-dansullivan-private.txt
    ```
    
    Make sure the keys are installed
    
    ```
    gpg --list-keys
    gpg --list-secret-keys
    ```
     
4. Delete the exports

    ```
     rm -rf ~/gnupg-dansullivan-public.txt
     rm -rf ~/gnupg-dansullivan-private.txt
     ```
5.  Test the recovery
    1.  Clone the blackbox demo
        
        ```
        cd /tmp && rm -rf blackbox-demo \
        && git clone https://github.com/deepeeess/blackbox-demo.git && cd blackbox-demo
        ```
    2. Test the ability to decrypt the file
        
        ```
        blackbox_edit secret_data.txt.gpg
        ```
    
# Reference

[blackbox-demo](https://github.com/dsulli99/blackbox-demo)
