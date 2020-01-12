# crDroid build script #

### Description ###

This bash script is used to build crDroid and upload via FTP.  
With proper settings, it's also possible to push to crDroid SourceForge page automatically.

### How to Install

In order to install this, all it's needed to be done is copy build script locally, set it as executable and configure it with built-in wizard.  
To do so run following commands in terminal:

```bash
# Download the script with curl
$ curl -LJO https://raw.githubusercontent.com/crdroidandroid/crdroid_build/10.0/build
# Make script executable
$ chmod +x build
# run the script
$ ./build
```

### Configuration

You now need to configure build script and add device codenames that you want to build for.  
For that just issue **./build** in terminal and follow the on-screen instructions.

```bash
$ ./build
$ Please enter the path where crDroid folder is located (full path ex:/home/<user>/crDroid)
$ /home/user/crDroid
$ Upload compilation to remote server at end of build?
$ 1 or 2 (Yes/No)
$ Enter remote hostname (ex: upme.crdroid.net):
$ upme.crdroid.net
$ Enter remote username::
$ user
$ Enter remote password:
$ myultrasecurepassword
```

Now as you just set your configuration, next step would be to add a devices to initiate build for.  
Running **./build add** will prompt you to enter your device information.  

```bash
$ ./build add
$ Add a new device:
$ Format: <device codename>,<remote upload path>
$ guacamole,/files/guacamole/6.x
```


### Additional stuff (optional and not mandatory)

If you want for example to repopick some unmerged commits, just create a repopick.txt file, and add your stuff there.  
Build script will execute them after repo sync 

### Start building

In order to start building, issue the following command in terminal

    $ ./build

### Help

Issue **./build help** in terminal for a list of helpfull commands

```bash
This build script is used to be able to build crDroid and upload the builds to remote server
Usage: ./build [OPTION]

Commands supported:
add       - adds a device to be built
remove    - removes a device from build list
list      - lists all devices that are configured to be built
clean     - cleans up the configuration
clear     - clears up all the devices on build list
```
