# ssh-user

Add multiuser capabilities to your ssh.

---
This simple program replaces the private-key reference in your `.ssh/config`, and thus
allows you to switch to different keys that are located in different github repositories.

After you have generated your ssh keys, and you have more than 2 keys in your `.ssh` folder, 
type in the name of the key (ex: `id_rsa`) as an argument to the console. 

### Switching
```shell script
$ ssh-user 0x0042
```

```shell script
$ ssh-user id_rsa
```

### Flags

For help type
```shell script
$ ssh-user -help
```

To select a specific host
```shell script
$ ssh-user -host=github.com id_rsa
```

To use a different config file
```shell script
$ ssh-user -config ./my/working/directory id_rsa
```