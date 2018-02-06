# Uninstalling Anaconda or Miniconda

## Mac OSX

1. Open a Terminal window.

2. Remove the entire Miniconda install directory with:

```
rm -rf ~/miniconda
```

3. You may also:

OPTIONAL: Edit ~/.bash_profile to remove the Miniconda directory from your PATH environment variable.

4. Remove the following hidden file and folders that may have been created in the home directory:

.condarc file
.conda directory
.continuum directory

By running:

```
rm -rf ~/.condarc ~/.conda ~/.continuum
```

## Windows

1. In the Windows Control Panel, click Add or Remove Program.
2. Select Python X.X (Miniconda), where X.X is your version of Python.
3. Click Remove Program.

NOTE: Removing a program is different in Windows 10.