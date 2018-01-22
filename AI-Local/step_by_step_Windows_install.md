# Installation Instructions for Windows

The following instructions will *not* use a Docker image, but rather enable you to install the necessary components locally onto your machine.

## Installing Anaconda

[Anaconda](https://en.wikipedia.org/wiki/Anaconda_(Python_distribution)) is a freemium open source distribution of the Python and R programming languages for large-scale data processing, predictive analytics, and scientific computing, that aims to simplify package management and deployment. It will also enable us in install TensorFlow and other packages.

1. Go to https://www.anaconda.com/download/ and download the Windows installer. (Note: Choose the most recent version of Python unless you have a specific reason not to.)

2. Run the installer. This can take a while (5-15 minutes). There are a lot of files. (Note: Near the end a Command window will open. This is normal.) Once you're done, in your installed programs you should, among other things, have Anaconda Navigator, Jupyter Notebook and Spyder.

![Anaconda Installation](../imgs/anaconda-install.png)

3. To make sure that everything is up to date, which is almost never the case, even with a fresh install, open the Anaconda Prompt, which is an application that will be found in the new Anaconda folder. (Note: The Anaconda Prompt is just like the Command Prompt, however, it ensures that you are able to run Anaconda and Conda commands without have to change directory.) Run `conda update conda` and then `conda update --all`. For both of these, when requested to proceed, enter "y". (Note: The 2nd command should include an update of conda, however, it's been noted that doing these in two steps can sometimes avoid some crashing.)

`conda list` will give you a list of everything installed along with the version numbers.

## Setting up Anaconda Environment and Installing TensorFlow

The [instructions](https://www.tensorflow.org/install/install_windows) for installing TensorFlow immediately point to two options: with CPU support only or with GPU support. The latter will give you better performance, but it's significantly more complicated and will require installing a lot of NVIDIA stuff, some of which requires approval for a NVIDIA developer account. That may take days, so let's go with CPU support only. (Note: If you'd like to try to install with GPU support you should go for it because it is awesome. Once all the NVIDIA stuff is in place, you'll have to make one small change below, which is `pip install --ignore-installed --upgrade tensorflow-gpu`. You can always come back and do this later, too.)

1. Create a Conda environment named "tensorflow" by running `conda create -n tensorflow` in the Anaconda Prompt. Reply "y" at the prompt asking to proceed. (Note: This will, by default, include the version of Python installed.)

2. Activate the environment by running `activate tensorflow`. (Note: Your prompt should change to something like `(tensorflow) C:>`.)

3. To install the CPU only version of TensorFlow into the environment, run `pip install --ignore-installed --upgrade tensorflow`. (Note: If you run `conda list` and see that "tensorflow" is already there, then it came preinstalled with your Anaconda. Reinstalling it won't hurt, but this step might be superfluous.)

If you get a pop-up windows that says, "Missing shortcut: Windows is searching for python.exe," you can click the button to tell Windows where to find it (saving you a ton of time) and then navigate to `C:\Users\{your-user-name}\Anaconda3`. python.exe should be in there.

## Test your Installation in Jupyter Notebook

You should now be ready to give it a whirl.

1. From the Anaconda Prompt, *inside your "tensorflow" environment*, run `jupyter notebook` and your default browser should open to `http://localhost:8888/tree` with the Jupyter logo at the top.

2. Create a new kernel by clicking the **New** button on the top right and selecting **Python 3** in the drop down menu. This will launch a new browser tab with an empty and untitiled notebook.

3. On the first line in the notebook, copy and paste the following code:

```
import tensorflow as tf
hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
print(sess.run(hello))
```
4. Execute the code by pressing **shift** + **enter** simultaneously

5. You will know your installation is successfull if the jupyter notebook returns

```
'Hello, TensorFlow!'
```
(Note: If you get a warning of the type `C:\Users\Mark\Anaconda3\lib\site-packages\h5py\__init__.py:34: FutureWarning: Conversion of the second argument of issubdtype from 'float' to 'np.floating' is deprecated. In future, it will be treated as 'np.float64 == np.dtype(float).type'. from ._conv import register_converters as _register_converters` you may ignore that.)

## Cloning the Repository

Congratulations on making it this far! You've installed everything you need for deep learning with TensorFlow and you're Anaconda environment is set up and working. Your next step is to clone the AccelAI Github repository to your local machine. Since these instructions are *not* using Docker, or any other virtual machine, we'll be cloning the Github repository to a local directory.

1. Inside the Anaconda Prompt, navigate to the directory where you wish to clone the repository, like `C:\Users\Mark\Documents\GitHub`. (Note: `cd /` will take you to the home directory, `cd ..` will take you up one leverl, `dir` will list all of the files and folders in your current directory and `cd` followed by the folder name will take you into the directory. `cd c:\Users\Mark\Documents\GitHub` will take you directly to that directory, assuming the path is correct. You'll probably have to replace `Mark` with your own user name.)

2. Once you're in the desired directory, enter `git clone https://github.com/AccelAI/Image-Classification-TensorFlow.git`. The repository is almost 500MB so it might take a few minutes to clone.

## Open the Lab Instructions

1. Switch into the directory where you have cloned the Github repository. If you'll followed the instructions above, `cd Image-Classification-TensorFlow` will probably get you then.

2. Inside the Anaconda Prompt, if you're not in your TensorFlow environment (the prompt will start with something like `(tensorflow) c:\...`), enter `activate tensorflow`. (Note: See above if you have questions.)

3. Enter `jupyter notebook` to launch the Jupyter notebook, which should automatically open a tab in your default browser. (Note: If it seems like you're not in the directory where you're supposed to be, close the tab and terminate Jupyter notebook in the Anaconda Prompt by typing Ctrl-C twice. Enter `jupyter notebook --generate-config` in the Anaconda Prompt and selected "y" when prompted. Try `jupyter notebook` again and it should work.)

4. In your browser, click "notebooks" and then "TensorFlow_for_Poets_Codelab.ipynb". This should open a new tab where you'll continue to follow the instructions.
