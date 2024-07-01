---
name: Bug report
about: Create a report to help us improve
title: 'The function r.setVolumeUp  mutes right channel'
labels: bug
assignees: ''

---

**Describe the bug**
Using the kt0915_99_minimal_receiver example from the library file I added volume control using r.setVolumeUp() and r.setVolumeDown(). I assigned those to extra pins and the functionality is OK for volume Down. When I use volume Up and increase volume level over 27, however, the right channel is muted. decreasing volume below 28 will bring it back. This behaviour was also observed in the serial command for volume "+" in the "KT0915_01_AM_FM.ino"

**To Reproduce**
Upload "KT0915_01_AM_FM.ino" to an Arduino. Run the serial monitor. Input "+" several times unitl the volume level is 28 or more. The right channel will mute. Press "-" and when the volume is 27 or less the right channel will come back. 

**Expected behavior**
Expected bahaviour is that the volume will increase on both left and right channel until the maximum 31 is reached.

**Screenshots**
If applicable, add screenshots or photo to help explain your problem.

** Please, add the following information):**
 - Arduino IDE version: 2.3.2 (Linux Mint)
 - Arduino Board: Nano with old boot loader
 - Library version: 1.0.3

**Additional context**
At first none of the exampples worked. I needed to add:
#include <Wire.h>
and in the "void setup" section
Wire.begin();
For the sketch to work. Otherwise it will not control or find the KT0915
