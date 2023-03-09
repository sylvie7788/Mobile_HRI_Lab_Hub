# Make the robot see
**List the names and NetID for your partners here.**

Hongyu Shen hs692, Sylvie Chen xc455, Haohua Liu hl766, Tsung-Yin Hsieh th542, Jonathan Tan jmt362

Build off of Lab 3 from last week. This week's material can be done rather quickly.


## Prep

### For this lab, you will need:
1. Your laptop
2. Pi Camera

### Before you come to the lab on Thursday, please do the following:
1. Install VNC viewer from [here](https://www.realvnc.com/en/connect/download/viewer/) if you haven't. 

### Deliverables for this lab are: 

0. A screenshot of the working VNC viewer with a working image view.

1. Answers to the reflection questions in Part D. 

### The Report 
This README.md page in your own repository should be edited to include the work you have done (the deliverables mentioned above). Following the format below, you can delete everything but the headers and the sections between the **stars**. Write the answers to the questions under the starred sentences. Include any material that explains what you did in this lab hub folder, and link it in your README.md for the lab.

## Lab Overview
For this assignment, you are going to:

A) [Connect your camera](#-a-connect-your-camera)

B) [Connect to your Pi (VNC Viewer)](#part-b-connect-to-your-pi-through-vnc-viewer)

C) [People Detection](#part-c-people-detection)

Labs are due on Tuesdays before class. Make sure this page is linked to on your main class hub page.

## Part A. Connect your camera
Plug in the Pi camera to your RPi.

## Part B. Connect to your Pi through VNC Viewer
Start VNC Viewer, if prompted to sign in, "select Use VNC without signing in" in the bottom.

In the text box "Enter a VNC Server address or search", type in `Your_RPi_IP:1` (e.g. `10.56.131.31:1`).
> When prompted "server not encrypted", click "continue"
<img src="Images/vnc_warning.jpg" width="300">

**Password**: `student`

You should now log in to your Pi through VNC Viewer.

> <img src="Images/vnc.jpg" width="300">

Open a terminal, install `libcamera-dev`.

```bash
sudo apt install libcamera-dev
```
> <img src="Images/terminal.jpg" width="300">

## Part C. People Detection
First, let's test if your camera is working properly. 
```bash
# In a terminal in VNC Viewer
cd
curl -LJO https://raw.githubusercontent.com/FAR-Lab/Mobile_HRI_Lab_Hub/main/Lab4/test_camera.py
python3 test_camera.py
```
**Please include a screenshot of the working VNC viewer with a working image view.**

<img width="1136" alt="Screen Shot 2023-02-23 at 11 46 18 AM" src="https://user-images.githubusercontent.com/6706384/220973916-eb6fec9b-8c5e-4fa8-910f-4c12e68001d1.png">

This exercise is based on this [The Data Frog Tutorial](https://thedatafrog.com/en/articles/human-detection-video/#:~:text=People%20detection,work%20well%20in%20other%20cases.) online. Your CPU will get toasty, so put on a **heat sink**. 

```
# In a terminal in VNC Viewer
curl -LJO https://raw.githubusercontent.com/FAR-Lab/Mobile_HRI_Lab_Hub/main/Lab4/people_detection.py
python3 people_detection.py
```
<img width="1092" alt="Screen Shot 2023-02-23 at 11 55 04 AM" src="https://user-images.githubusercontent.com/6706384/220976023-1bd8219f-f437-4195-a144-d47890334451.png">

Optional: Another example you can try is from [PyTorch](https://pytorch.org/tutorials/intermediate/realtime_rpi.html) (installed already on your system). You will need to write a few lines of code to load the labels yourself. 

## Part D. Reflection

Reflect on the following questions:

1. For your favorite prototyped interaction that you have thought of so far, reflect upon how a camera connected to your Pi could be useful.

A camera connected to the pi is paramount to every single interaction we have considered.  From identifying plants to water, identifying people to provide service, animals for photography and buildings for navigation, the camera is essential.

3. What issues do you foresee with this setup? 

The simple solution with adding a camera is not enough to consider.  We have to consider how the camera will be housed, how it will be protected, whether or not it will be mobile.  We must also consider the factors regarding computing power, speed of processing, and network reliability.  The physical ribbon cable connection for the camera appears to be weak.

5. How is the temperature? How is the speed? How is the connection?

The speed is quite abysmal.  In several instances the display lag was well over 10 seconds.
As far as temperature goes, we mitigated this effect by applying heatsinks to several chips located on the raspberry pi 4.  The connection was good via WIFI, however we do believe this connection can improve if we refrain from streaming the video feed back to the VNC viewer via RedRover network.

6. How is the view? Would it capture what you might need to see for your prototyped interaction (in question 1)?

The view is quite limited, resolution is weak, and artifacts and pixellation are rampant.  How useful it will be would come down to testing and computer vision techniques (sampling, stitching etc.). We believe however, despite the fact that this camera does not perform akin to the human eye, it is immensley powerful and will only be limited by our ability to adapt.

Labs are due on Tuesdays before class. Make sure this page is linked to on your main class hub page.

### Again, deliverables for this lab are: 

0. A screenshot of the working VNC viewer with a working image view.

1. Answers to the reflection questions in part D. 

