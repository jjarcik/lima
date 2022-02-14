# Lima + Vscode + Docker -> Superfast
How to use lima and have docker on MacOs super fast

## Prepare (only once)
1. install lima
https://github.com/lima-vm/lima

2. terminal
- limactl start  
- Creating an instance "default" Open an editor to override the configuration with file lima.txt

3. Host file
- open ~/.ssh/config
- add:

```
 Host your-name
  StrictHostKeyChecking no
  User YOUR_USER_NAME
  HostName 127.0.0.1
  Port 60022
  IdentityFile ~/.lima/_config/user
```

## Use
start lima

```bash
$ lima
$ cd ~
$ mkdir dev
$ git clone ....
$ docker-compose up
```

## Vscode
- Install plugin https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh
- click in the bottom-left corner of vscode on green icon
- select Connect to host, thene select `your-name`
- open your dev folder with project and happy to code :)


### Fix troubles
#### Git login with ssh
eval `ssh-agent -s` && ssh-add /Users/YOUR_NAME/.ssh/id_rsa
