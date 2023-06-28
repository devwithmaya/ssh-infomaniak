
# Hosting on a shared via SSH (Infomaniak)

- Create a host-specific SSH key

- Create an SSH alias and add our public key

- Set up a remote git repository to version the project

- Put the sources online and prepare the basic configuration

- Configure the host to point the domain to the correct folder

## Creation of the SSH key
The first step will take place on our machine and we will generate a key specific to this host.

## Installation

Open your Git Bash and enter this command :

```bash
  ssh-keygen -t ed25519 -f ~/.ssh/infomaniak
```
    
On the Infomaniak side, we are going to create a new SSH user by going to the FTP/SSH section . To simplify the SSH connection we will, on our machine, create an alias by modifying the configuration file ``` ~/.ssh/config ```

```bash
  Host maya
    HostName x0000.ftp.infomaniak.com
    User x0000_artco
    IdentityFile ~/.ssh/infomaniak
    IdentitiesOnly yes
```
