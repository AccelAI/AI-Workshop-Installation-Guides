# Uninstall or Reset Docker

## Mac OSX

### GUI
1. Choose whale menu -> Preferences from the menu bar, then click Uninstall / Reset on the Preferences dialog.

2. Uninstall or reset Docker

3. Remove all data - This option removes/resets all Docker data without a reset to factory defaults (which would cause you to lose settings).

4. Uninstall - Choose this option to remove Docker for Mac from your system.

5. Reset to factory defaults - Choose this option to reset all options on Docker for Mac to its initial state, the same as when it was first installed.

### Uninstall from the command line

Alternatively, you can uninstall Docker for Mac from the command line with this command: 

```
<DockerforMacPath> --uninstall
``` 

If Docker is installed in the default location, the following command provides a clean uninstall.

```
$ /Applications/Docker.app/Contents/MacOS/Docker --uninstall
Docker is running, exiting...
Docker uninstalled successfully. You can move the Docker application to the trash.
```

You might want to use the command-line uninstall if, for example, you find that the app is non-functional, and you cannot uninstall it from the menu.


## Windows

### How to uninstall Toolbox

Removing Toolbox involves removing all the Docker components it includes.

A full uninstall also includes removing the local and remote machines you created with Docker Machine. In some cases, you might want to keep machines created with Docker Machine.

For example, if you plan to re-install Docker Machine as a part of Docker for Windows you can continue to manage those machines through Docker. Or, if you have remote machines on a cloud provider and you plan to manage them using the provider, you wouldn’t want to remove them. So the step to remove machines is described here as optional.

To uninstall Toolbox on Windows, do the following:

1. List your machines.

```
$ docker-machine ls
NAME                ACTIVE   DRIVER       STATE     URL                        SWARM
dev                 *        virtualbox   Running   tcp://192.168.99.100:2376
my-docker-machine            virtualbox   Stopped
default                      virtualbox   Stopped
```

Optionally, remove each machine. For example:

```
$ docker-machine rm my-docker-machine
Successfully removed my-docker-machine
```

This step is optional because if you plan to re-install Docker Machine as a part of Docker for Windows, you can import and continue to manage those machines through Docker.

2. Uninstall Docker Toolbox using Window’s standard process for uninstalling programs through the control panel (programs and features).

Note: This process does not remove the docker-install.exe file. You must delete that file yourself.

3. Optionally, remove the C:\Users\<your-user>\.docker directory.

If you want to remove Docker entirely, you can verify that the uninstall removed the .docker directory under your user path. If it is still there, remove it manually. This directory stores some Docker program configuration and state, such as information about created machines and certificates. You usually don’t need to remove this directory.

4. Uninstall Oracle VirtualBox, which is installed as a part of the Toolbox install.