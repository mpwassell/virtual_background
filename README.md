# Virtual Camera Background
Code for creating virtual background for conference calls based on https://elder.dev/posts/open-source-virtual-background/

Extends knowledge of Docker and TensorFlow.

If running outside of Docket, will need to install requirements for fakecam container.
See fakecam/requirements.txt for list

On the host, need to do:
```
sudo apt install v4l2loopback-dkms
sudo modprobe -r v4l2loopback
sudo modprobe v4l2loopback devices=1 video_nr=20 card_label="v4l2loopback" exclusive_caps=1
```

# Notes on using camera with VirtualBox
Use USB 3.0 controller.
Under Devices, select camera from USB menu *not* Webcams.


