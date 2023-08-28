---
layout: page
title: ArduinoBot
description: C++, 3D-Printing, SolidWorks
# The Arduino That Walks.
img: assets/video/ArduinoBot.gif #img/arduinobot_on_table.jpg
importance: 1
category: work
related_publications:
---

---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/video/ArduinoBot.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Over the summer of 2022, I devised a plan to design, program and build a compact 3D printed bipedal robot. My objectives and final outcomes of this project were as follows:

---

| Objective                             |                                   Final outcome |
| :------------------------------------ | ----------------------------------------------: |
| Minimize Complexity                   |       30 individual parts (including fasteners) |
| Minimize Manufacturing Time           | Takes <3 hours to print and <30 min to assemble |
| Minimize Cost                         |                                      Costs <$30 |
| Minimize Weight                       |                       Uses only 18g of filament |
| Maximize Travel Speed & Stride Length |                   Moves lightning fast (~8mm/s) |

<br />

## Design Rationale

---

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
My little friend started as a sketch in OneNote (on the right). The idea was to make a statically stable robot that moved by lifting a foot (1), rotating its body forward (2), lowering the foot (3) and repeating with the opposite foot. However, because the dark blue servos are arranged horizontally and the light blue servos are directly vertical, all the gravitational load is being put on the light blue servos. The dark blue servos would only have to overcome the inertia of the robot, which is comparatively small.<br /> <br />

{% include figure.html path="assets/img/AB_45deg_markup.png" title="example image" class="img-fluid rounded z-depth-1" %}

<div class="caption">
    Final design with "sawtooth" gate (diagonally up, diagonally down, repeat)
</div>

</div>
<div class="col-sm-6 mt-3 mt-md-0">
{% include figure.html path="assets/img/AB_prelim_sketch.png" title="example image" class="img-fluid rounded z-depth-1" %}

<div class="caption">
    Initial concept sketch with square gate (up, forward, down, repeat).
</div>

To reduce this load imbalance, I opted to tilt the body of my robot forward by 45 degrees (as shown on the left). This changed the motion from a square gate (servo 1 up, servo 2 forward, servo 1 down, repeat) to a "saw-tooth" gate (motor 1 diagnoally up, servo 2 diagonally down, repeat)depicted below. By making this small change, both servos are each only experiencing a faction of the gravitational load; specifically mg/sqrt(2). This ensures that I get the most torque possible out of each servo.

</div>
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        ArduinoBot was designed to be as simple and lightweight as possible. The final design contains only five 3D printed parts that together weigh only 18g. Using a standard 9V battery and the cheapest servos I could possibly find also allowed me to keep my budget under $30.
        <br /> <br />
        ArduinoBot was also designed to keep the center of mass close to the pivot points of each servo. This meant keeping the design compact and mounting the battery (by far the heaviest component) in the core of the robot directly adjacent to the servos.
        <br /> <br />
        Another important design decision was the size of ArduinoBot's feet. It's toes are long enough to be keep the robot statical stable at all times (in other words: long toes = good balance). However, the feet are also small enough that they (mostly*) don't get in the way of eachother.
        <div>
            <small>* there is a little bit of rubbing between the feet which could be improved with more trial and error on the robot's software.</small>
        </div>
        <br />
    </div>
    <div class="col-sm-7 mt-3 mt-md-0">
        {% include figure.html path="assets/img/arduinobot_exploded_long.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
        Exploded view of final design.
        </div>
    </div>

</div>

## Final Thoughts

---

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/arduinobot_walking_cropped.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
        Render of ArduinoBot just walkin around.
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        Overall, ArduinoBot was a very fun project and challenged me to apply my knowledge of CAD (specifically SolidWorks), 3D-printing and robot control using C++.
        <br /> <br />
        In the future, I could improve ArduinoBot in the following ways: First, I would add a joystick controller and program ArduinoBot to move forward, backward, left or right. Second, I would upgrade to a better battery (such as Li-ion or LiPo), replacing the 9V battery which drains completely in just a few minutes due to the high current draw from the servos. Finally, I would upgrade to higher quality servos, which would allow ArduinoBot to carry a larger battery and take bigger steps.
    </div>
</div>

{% raw %}

{% endraw %}
