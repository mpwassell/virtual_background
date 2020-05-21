# Virtual Camera Background
Code for creating virtual background for conference calls based on https://elder.dev/posts/open-source-virtual-background/

# Installation/setup


On the host, need to do:
```
sudo apt install v4l2loopback-dkms
sudo modprobe -r v4l2loopback
sudo modprobe v4l2loopback devices=1 video_nr=20 card_label="v4l2loopback" exclusive_caps=1
```

If running outside of Docker then you will need to install requirements for fakecam container.
See fakecam/requirements.txt for list


# Notes on using camera with VirtualBox
Use USB 3.0 controller.
Under Devices, select camera from USB menu *not* Webcams.

# To run outside Docker

Do
sudo modprobe v4l2loopback devices=1 video_nr=20 card_label="v4l2loopback" exclusive_caps=1

In bodypix directory do: node app.js
In fakecam directory do: python3 fake.py

# Status
Poor performance makes this non-feasible for actual conference call. Investigate reducing how often we recalculate
the mask. Fall back onto an approximate method that relies on the picture and hence what is the background changing
much for each frame.


