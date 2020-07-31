# ssh-user

Add "multiuser" capabilities to your ssh.

---
This simple script replaces the private-key reference in your `.ssh/config`, by doing this
simple modification, we can switch keys on the fly, and gives us a "multi-user" capabilities.

If you have multi-github accounts, this script will allow you to push changes to your selected account
given that you have the ssh private key.

### Basic how to use.
```shell script
$ ssh-user [-flags] [argument]
```
__flags should be defined before the arguments__

### List all available flags
```shell script
$ ssh-user -help
```
```shell script
  -config string
        default config file of the SSH,  (default ".ssh/config")
  -help
        display help message of the command line
  -host string
        Set the default host value you want to target (default "*")
  -list
        List the configurations in .ssh/config file
```

### Switching Users
Given that you have the following
```shell script
-rw-------  0x0042 # Private Key
-rw-r--r--  0x0042.pub # Public Key
-rw-r--r--  config # Your config file
-rw-------  id_rsa # Private Key
-rw-r--r--  id_rsa.pub # Public Key
-rw-r--r--  known_hosts # Not an account
```
Each key represents a acconnection to an "account".

#### Switching Users
```shell script
$ ssh-user 0x0042
```

```shell script
$ ssh-user id_rsa
```

#### Using Flags

To select a specific host
```shell script
$ ssh-user -host=github.com 0x0042
```

To use a different config file
```shell script
$ ssh-user -config ./my/working/config 0x0042
```

To list the config file
```shell script
$ ssh-user -list
```