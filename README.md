# VVVV.KTools
I build this repo to store some of the patches I think useful during my learning process. You can download them and see how I solve my problems, or even use them to do whatever you want.
# How to use them as subpatches?
To use my patches as subpatches, simply clone the one suits your need to your computer, then change the filename from XXX.XML to XXX.V4P. Voila! Now you've got a functional subpatch ready at your service. Drag and drop it to your main patch and let it do its work. If you're not sure how it works, just right click the node, and you can see I prepared a short intro in it.

Note: In order to open the demo_xxx file properly, you need to put both demo file and the corresponding subpatch file under a same directory, or otherwise it will show red in the patch. If they are still showing red regardless, just find the matching subpatches and drag them into the demo patch then connect all the pins manually (shouldn't be too hard).
# Just read the instructions.
I'm currently working on KinectV2, so there will be a lot of nodes coming from DirectX11.nodes pack. You might wanna make sure you installed KinectV2 SDK or runtime properly. You can follow the guide here to setup your Kinect:

<a href="https://vvvv.org/documentation/kinect">https://vvvv.org/documentation/kinect</a>
## 1_KinectLightControl
This patch is designed to control lighting with your hand. Use GetSlice to get the positionXYZ of a spesific joint, then map the range accordingly for a better result.

Note that this solution is not perfect. If you rotate around the geometry, it might looks weird. In my case, I use it with Kinect2Face. And since the camera is always facing towards -z, the controlling works nicely.
## 2_StepCounter
I build it in one of my recent project. I have multiple video footage, and I want to switch them one by one when I swipe my hand. But I cannot simply just GetSlice, boolean the positionX and use counter to switch, for it will keep counting. I need a module that only bang once. So this is it. This subpatch receives an input value that is constantly changing, and compare it to the baseline value. If the input is higher than baseline, add 1 to the count.
