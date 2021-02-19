# smplify-x_in_docker
(English translation via translate.google.com)

## Introduction
Smplify-x is a human body 3d mesh prediction network based on SMPLx developed by Max Planck, Germany. Because it is very difficult to configure the environment when reproducing, this method of configuring docker is written. After the configuration is completed, you can run smplify directly in the docker container.

The use of docker is mainly based on the following two points:
* smplify-x cannot use anaconda to configure the virtual environment, and it often reports errors.
* Using virtualenv may not go wrong, but to be safe, it is better to use a container.


## Run
First download the dockerfile and all required installation packages and enter the project folder
```Shell
git clone https://github.com/wells-wei-wei/smplify-x_in_docker
cd smplify-x_in_docker
```
Remember to download the smplx model from Max Planck’s official website (https://smpl-x.is.tue.mpg.de/), and put the decompressed models folder in smplify-x_in_docker (just overwrite it) )
, And then create a mirror in the folder
```Shell
docker build -t smplx/smplify-x:v1.
```
The whole process takes a long time, please be patient

After completion, create the container:
```Shell
docker run -it --runtime=nvidia -P smplx/smplify-x:v1
```
Then enter the container, you can see the smplify-x project file in /home, and run after entering
```
python3 smplifyx/easy_run.py
```
You can complete the demo

## About SSH
In order to facilitate debugging, the content of installing ssh and setting remote login is added to the dockerfile, which is suitable for small partners who use the server, and can be deleted if not needed
