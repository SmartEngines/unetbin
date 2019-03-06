# U-Net-bin: DIBCO 2017 Submission

This page is concerned to our submission that was ranked first in the Document Image Binarization Contest 2017 (DIBCO). It  is  a  convolutional  neural  network (CNN)  based  method  which  uses  U-Net  architecture. A  docker container with the network along with all the supplementary data we used in the training process has been released at [ftp://smartengines.com/unetbin](http://tinyurl.com/yybhde3m). Folders  `printed` and `handwritten` contain grouped images from the previous DIBCO contests. Ground truth prepared by organizers is located in folders with `_gt` suffix. In the `aux` folder there are images we have additionally selected and used during the learning procedure.

## Prerequisites

Install the latest version of Docker.

## Usage

* Download the docker image
```
wget ftp://smartengines.com/unetbin/dibco_06-30.tar
```
* Unpack the docker image
```
docker load <dibco_06-30.tar
```
* Start the running image
```
docker run -dt --name dibco -v <local-folder-name>:/mnt/volume dibco:06-30 /bin/bash
```
* Execute
```
docker exec dibco /root/environment/bin/python /root/evaluate_answer.py -i <input-image-name> -o <output-image-name>
```
