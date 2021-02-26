# Type-In-Space
# 2021/2/16
Tutorial video link : https://www.youtube.com/watch?v=unbmO58cLn0
## 01 Overview
## 02 Project Setup
1. Unity 2019.4.17
2. MRTK 2.5.3
3. Visual Studio 2019
## 03 Text Object - Gran and Move
1. 创建文字 3D Object -> Text - Text Mesh Pro。
2. 修改文字大小（参照物为0.1倍大小的Cube），字体，位置格式。
3. 添加Box Collider。
4. 添加ManipulationHandler组件，将文字赋值到Host Transform。
5. 添加NearInteractionGrabbable组件，选择Show Tether When Manipulating为true。
6. 添加Audio Source，在Manipulation Events中的On Manipulation Started时间中注册AudioSource.PlayerOneShot方法，添加MRTK_Move_Start音频文件；在On Manipulation Ended时间中注册AudioSource.PlayerOneShot方法，添加MRTK_Move_End音频文件。
## 04 Text Object - Scale, Rotate with Bounding Box
1. 在文字上添加BoundingBox组件
2. 从BoundingBoxExample场景中，获取CoffeeCup1上的BoundingBox组件的参数，赋值给文字的上。
3. 将文字赋值到Target Object和Bounds Override。将Flatten Axis设置成Flatten Z。
## 05 Text Object - Bounding Box Polish
1. 在BoundingBox组件的Events上，添加对应事件的音频。
2. 将BoundingBox材质里的Ignore z Scale勾选上。
3. 将BoundingBoxGrabbed材质里的Ignore z Scale勾选上。
4. 将Box Padding设置成 (0.01, 0.01 ,0.01)。
## 06 Toolbar Design - 1 Grid Object Collection
1. 创建一个空物体，命名为Toolbar。
2. 在Toolbar里创建一个空物体，命名为ButtonCollection。
3. 添加6个PressableButtonHoloLens2Unplated。
4. 在ButtonCollection上添加GridObjectCollection组件。
5. 将Num Row设为1，Cell Width和Cell Height设为0.03，然后Update Collection。
## 07 Toolbar Design - 2 Tag along with Solver
在Toolbar上添加RadiaView组件，将Move Lerp Time和Rotate Lerp Time设置成2.5，Min Distance设置为0.3，Max Distance设置为0.6，把Use Fixed Vertical Position勾选上，把Fixed Vertical Position设置为-0.3。
## 08 Toolbar Design - Button Icon Updates

