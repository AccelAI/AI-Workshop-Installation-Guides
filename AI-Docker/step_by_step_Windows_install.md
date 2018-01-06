# Installation Instructions for Windows

## Installing Docker

Docker is a system to build self contained versions of a Linux operating system running on your machine. When you install and run Anaconda packages via Docker it completely isolates the installation from pre-existing packages on your machine.

**Windows 10 Enterprise or newer:**

1. Download the Docker installer [here](https://download.docker.com/win/stable/InstallDocker.msi).

2. Run ‘InstallDocker.msi’

3. Launch Docker when the installer finishes

If Docker warns you about Hyper-V not being enabled, allow Docker to enable Hyper-V and automatically restart your machine

4. Open PowerShell or ‘cmd.exe’ and run the Docker hello-world image to ensure Docker is working properly

```
docker run hello-world
```

**Windows 7**

The legacy solution for older Windows systems is Docker Toolbox.

https://docs.docker.com/toolbox/toolbox_install_windows/

Click on the "Get Docker Toolbox for Windows" button. 

Follow their instructions to install Docker and to make sure that virtualization is enabled on your machine.

## Pull Docker Image

These are images adapted from one created by [wise.io](http://wise.io) datascience [git repo](https://github.com/wiseio/datascience-docker), with the underlying python distribution coming from [Continuum/Miniconda](http://continuum.io).  We've pre-installed the following to get you started:

  - _graphviz_ 
  - _jupyter_ 
  - _keras_ 
  - _pandas_ 
  - _pytorch_ 
  - _scipy (numpy & matplotlib)_
  - _scikit-learn_ 
  - _seaborn_ 
  - _tensorflow_ 
  - _theano_ 


This guide contains instructions using the latest distributions of Python3 and corresponding scientific packages. If you'd prefer to install a distribution for Python 2.7.11, [use this alternative guide](https://github.com/AccelAI/datascience-docker/tree/master/datascience-base_27).


**Python 3.6.1:**    

This Miniconda3-based image is hosted at the **Docker Hub**. You can grab it by:

1. Open PowerShell

2. Pull the docker image:

```
docker pull accelai/datascience-docker
```

3. Start a Jupyter Notebook interface:

```
docker run -it --rm --name tf -p 8888:8888 accelai/datascience-docker /bin/bash -c "/opt/conda/bin/jupyter notebook --notebook-dir=/opt/notebooks --ip='*' --port=8888 --no-browser --allow-root"
```

4. Copy the URL with your login Jupyter login token from PowerShell and go to it in your web browser


#### Test your Installation in Jupyter Notebook

At this point, your jupyter notebook will be empty since you haven't linked to any project directories. Test your installation of the miniconda distribution by following these steps:

1. Once Jupyter has launched an empty notebook tree in your browser, create a new kernel by clicking the **New** button on the top right and selecting **Python 3** in the drop down menu.

This will launch a new browser tab with an empty and untitiled notebook.

2. On the first line in the notebook, copy and paste the following code:

```
import tensorflow as tf
hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
print(sess.run(hello))
```
3. Execute the code by pressing **shift** + **enter** simultaneously

4. You will know your installation is successfull if the jupyter notebook returns

```
'Hello, TensorFlow!'
```
*Once you have successfully installed docker, the miniconda distribution, and tested your scientific packages, you are done with the install instructions!!* 

### Alternatively, Start the container via command prompt:

```
docker run -it --name tf accelai/datascience-docker /bin/bash
```

Test your installation of scientific packages in the Docker container - 
e.g. for TensorFlow in the command prompt execute the following:

    ````
    $ python
    ...
    >>> import tensorflow as tf
    >>> hello = tf.constant('Hello, TensorFlow!')
    >>> sess = tf.Session()
    >>> print(sess.run(hello))
    Hello, TensorFlow!
    >>> a = tf.constant(10)
    >>> b = tf.constant(32)
    >>> print(sess.run(a + b))
    42
    >>>

    ````

*Once you have successfully installed docker, the miniconda distribution, and tested your scientific packages, you are done with the install instructions!!* 

## Shutdown

### Jupyter
You can shutdown the Jupyter notebook server by returning to the powershell session that is running it and hitting the **ctrl** and **c** keys simultaneously on your keyboard.

### Docker

Before attempting to shutdown docker, check that docker processes are still running.

To list active docker containers in the powershell, execute:

```
docker ps
```

To stop the Docker container we created, execute the following:

```
docker stop tf
```

## Restart

You can restart the docker container and jupyter notebook at anytime by re-entering the **Start** commands above.