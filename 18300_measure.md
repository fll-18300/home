---
title: Team 18300 Robot Tape Measure
subtitle: Use the robot to measure distance
---

This code can be added to the Bolton Robotics base code to measure how far the robot moves (in mm) when pushed.  The robot can be used like a tape measure!

```python
def mission_seven(r):
    r.ev3.screen.clear()
    print("Team 18300 Robot Tape Measure")
    wait(4000)
    # Reset the distance to 0.
    r.robot.reset()
    btns = r.ev3.buttons.pressed()
    r.ev3.screen.set_font(Font(size=16, bold=True))
    while len(btns) == 0:
        r.ev3.screen.clear()
        r.ev3.screen.draw_text(0, 0, "Team 18300")
        r.ev3.screen.draw_text(0, 30, "Push robot to measure!")
        r.ev3.screen.draw_text(0, 60,"dst= " + str(r.robot.distance()))
        r.ev3.screen.draw_text(0, 90, "push btn 2 stop")
        wait(150)
        btns = r.ev3.buttons.pressed()
    # Set the font back
    r.ev3.screen.set_font(Font(size=30, bold=True))
```  
