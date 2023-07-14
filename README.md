
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
  ssh-keygen -t ed25519 -f ~/.ssh/project
```
    
On the Infomaniak side, we are going to create a new SSH user by going to the FTP/SSH section . To simplify the SSH connection we will, on our machine, create an alias by modifying the configuration file ``` ~/.ssh/config ```

```bash
  Host project
    HostName x0000.ftp.infomaniak.com
    User x0000_artco
    IdentityFile ~/.ssh/project
    IdentitiesOnly yes
```

This will make it easier for us to connect to this server by simply typing the command
```bash
  ssh project
```

To avoid having to enter the host's password every time we connect, we'll copy the public key generated at the beginning, using the "ssh-copy-id" command.
    
```bash
  ssh-copy-id -i ~/.ssh/project.pub project
```
