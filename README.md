# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

Step1:
Use from robomaster import robot
<br/>

Step2:
Choose the x,y,z - axis movement distance(meters).
<br/>

Step3:
Give ep_chassis.move to move straight.
<br/>

Step4:
Give time.sleep() for a break.
<br/>

Step5:
Give ep_chassis.drive_speed to have a circular movement.
<br/>

## Program
```python
from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera

    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)

    # Each inner list: [x, y, z, speed, r, g, b]
     
    actions= [[2.3, 0, 0, 0.5, 255, 153, 204],[0.5, 0, 45, 0.6, 255, 153, 204],[0.5, 0, 30, 0.7, 255, 153, 204],[0.4, 0, 30, 0.9, 255, 153, 204],[0.4, 0, 45,1.0,255,153,204],[0.7,0,45,1.2,255,153,204],[0.3,0,-35,1.5,255,153,204],[0.7,0,0,1.5,255,153,204]]


    for a in actions:
        x, y, z, xy_speed, r, g, b = a
        ep_chassis.move(x=x, y=y, z=z, xy_speed=xy_speed).wait_for_completed()
        ep_led.set_led(comp="all", r=r, g=g, b=b, effect="on")

    time.sleep(4)
    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()
```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

Insert image here

<img width="1600" height="1200" alt="image" src="https://github.com/user-attachments/assets/6f569dee-af13-44c8-ac3a-94a70f65f942" />


<br/>
<br/>
<br/>
<br/>

## MobileRobot Movement Video:

Upload your video in Youtube and paste your video-id here

https://youtu.be/AlJhey0UK64



<br/>
<br/>
<br/>
<br/>

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


<br/>
<br/>

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
