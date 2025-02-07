# SSH Key-Based Authentication Setup

## Generate an SSH Key Pair
```sh
ssh-keygen -t rsa -b 4096 -f ~/id_rsa
```

## Move Keys to the SSH Directory
```sh
mv ~/id_rsa ~/.ssh/id_rsa
mv ~/id_rsa.pub ~/.ssh/id_rsa.pub
```

## Set Proper Permissions
```sh
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
```

## Copy the Public Key to the Remote Server
```sh
ssh-copy-id -i ~/.ssh/id_rsa.pub usernamey@userip
```

## Test Passwordless SSH Access
```sh
ssh usernamey@userip
