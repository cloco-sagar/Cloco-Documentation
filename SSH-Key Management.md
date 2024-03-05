# SSH Key Management

## Introduction

SSH key management involves the generation, distribution, and secure storage of SSH (Secure Shell) keys used for authentication between systems.
It contains two parts i.e Public key(id_rsa.pub) and Private key(id_rsa). Public Key from SSH is inserted into the github account under the SSH Key in setting and Private Key from SSH is stored into the host system to authenticate the user.

##  Ways to generate SSH Key Pair on UNIX and UNIX-Like Systems

1. Run the ssh-keygen command.
   ```
   ssh-keygen -t rsa
   
   or
   
   ssh-keygen -t ed25519 -C "<email>" -f "<filename>" //Replace email and filename with your own filename
   ```
   You can use the -t option to specify the type of key to create.

2. The command prompts you to enter the path to the file in which you want to save the key.

   A default path and file name are suggested in parentheses. For example:
    ```
   /home/<user_name>/.ssh/id_rsa 
   ```
   To accept the default path and file name, press Enter. Otherwise, enter the required path and file name, and then press Enter.

3. The command prompts you to enter a passphrase.

   The passphrase is not mandatory. However, it is recommended that you specify a passphrase to protect your private key against unauthorized use.
    
4. When prompted, enter the passphrase again to confirm it.
5.  Test SSH connection:
    
    To ensure that everything is setup correctly, test the SSH connection to Github.
    ```
    ssh -T git@github.com
    ```

The command generates an SSH key pair consisting of a public key and a private key, and saves them in the specified path. The file name of the public key is created automatically by appending .pub to the name of the private key file. For example, if the file name of the SSH private key is id_rsa, the file name of the public key would be id_rsa.pub.

Now, You need to paste the id_rsa.pub key from .ssh folder into the github account under the SSH key section in github setting.

## REFERENCE LINK
https://docs.oracle.com/en/cloud/cloud-at-customer/occ-get-started/generate-ssh-key-pair.html#GUID-8B9E7FCB-CEA3-4FB3-BF1A-FD3406A2432F

## Knowledge Based
Problems you may encounter during ssh setup

### Problem 1: Pasting private key in Github instead of Public key from ssh

Remember that in .ssh folder there are two file upon the ssh key pair generation. Private key is with file name id_rsa and public key is with file name id_rsa.pub.

Insert the contents of id_rsa.pub into the github account under the section settings/SSH and GPG keys 

### Problem 2: Generate multiple SSH for using multiple github account in one System

```
ssh-keygen -t rsa -f ~/.ssh/<filename> -C <email_address>

Example:
ssh-keygen -t rsa -f ~/.ssh/personal -C personal@gmail.com
```

Create config file in .ssh folder and write these lines in config file.
```
Host github.com
  Hostname github.com
  IdentityFile ~/.ssh/id_rsa

Host github.com-personal
  Hostname github.com
  IdentityFile ~/.ssh/personal
```

Move to your project and setup git user config
```
cd <project_folder> // Replace project_folder with your own project_folder
git config user.email "<email_address>" // Replace email_address with your own email_address
git config user.name "<user_name>" // Replace user_name with your own user_name

Example:
cd cloco_project
git config user.email "cloco@gmail.com"
git config user.name "cloco"
```
