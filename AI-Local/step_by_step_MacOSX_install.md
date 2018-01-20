# Installation Instructions for MacOSX Locally

## Install Anaconda

1. Open the Terminal by clicking on the Spotlight magnifying glass at the top right of the screen, typing “Terminal” then clicking the Terminal icon.

2. Type the commands below to change into your Downloads directory and download Anaconda 4.4.0. Anaconda may take a few minutes to download.

```~ $ cd ~/Downloads```

```Downloads $ curl -O http://repo.continuum.io/archive/Anaconda2-4.4.0-MacOSX-x86_64.sh```

3. Type the command below to install Anaconda.

```Downloads $ bash ./Anaconda2-4.4.0-MacOSX-x86_64.sh```

4. Press **Enter** to read the license agreement. Use **Space** to continue to the next page.

```Welcome to Anaconda2 4.4.0 (by Continuum Analytics, Inc.)

In order to continue the installation process, please review the license agreement. Please, press ENTER to continue```

5. Type **yes** to accept the license terms.

```Do you approve the license terms? [yes|no]
[no] >>> yes```

6. Press **Enter** to install Anaconda to the default location.

```Anaconda will now be installed into this location:
/Users/username/anaconda2

- Press ENTER to confirm the location
- Press CTRL-C to abort the installation
- Or specify an different location below
[/Users/username/anaconda2] >>>```

8. Type **yes** to have Anaconda update your PATH.

```
Python 2.7.13 :: Continuum Analytics, Inc.
creating default environment...
installation finished.
Do you wish the installer to prepend the Anaconda install location
to PATH in your /Users/username/.bash_profile ? [yes|no]
[no] >>> yes
```

```Prepending PATH=/Users/username/anaconda/bin to PATH in newly created /Users/username/.bash_profile```


**For this change to become active, you have to open a new terminal.**

```Thank you for installing Anaconda!```

9. Open a new Terminal window by pressing **⌘-n**.

10. Type the command below to verify Anaconda was installed.

```~ $ python --version```
Python 2.7.13 :: Anaconda 4.4.0 (x86_64)

11. Type the command below to update Anaconda.

```~ $ conda update --all --yes```

## Start iPython Notebook

1. Type the command below to start iPython Notebook.

```~ $ ipython notebook```