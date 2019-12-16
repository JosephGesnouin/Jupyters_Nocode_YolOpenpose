#  YolOpenpose:
 
 **Combination of Yolov3 and OpenPose.**
 Hopefully the pose estimation inside each BB is better compared to a single-shot OpenPose.
 
 However, the computational time of the approach depends on number of detected people. Which is a huge loss in terms of efficiency if we contrast it to a 18 keyjoints OpenPose detection.
 
 **Few ideas to make the computation easier || more relevant:**
1. Keep the Cheating Setup: Signle Shot OpenPose && Signe shot Yolo on the entire Image, plot both of the results
2. Use another version of the OpenPose x Keypoints as some of them aren't invariant to number of detected people. (but less usefull for our specific Usecase)
3. Make a simple Pose Estimation and then min/max the (x,y) coordinates of each skeletons, to find a BB that fits the Pose. Doesn't add any information, but complexity wise becomes a more viable solution than the cheating setup. 

**Few random notes:**
 
 As the Pose Estimation are realised on the cropped images of the Yolo's BBs, some keypoints of OpenPose 18 keyjoints won't show. Maybe send a bigger cropped image with a treshold not to lose some information in space, however it could be potentially a problem in case of obstructions, multiple person being really closed to each others.
 
  
   
 
 Only Jupyters available, rest of the method will be uploaded anytime soon
