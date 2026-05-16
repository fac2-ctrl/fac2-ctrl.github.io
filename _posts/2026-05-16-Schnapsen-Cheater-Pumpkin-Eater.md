---
layout: post
title: Schnapsen Cheater, Pumpkin Eater!!
tags: [code]
author: Felix Crary
---

Hi Everyone! Here's my final project for the semester: the Schnapsen Cheater, Pumpkin Eater! I really love the card game Schnapsen, and one of the main functions of the game is that the player has to count their own points. Once the player gets to 66 points they must declare their victory or it doesn't count. But ya'know counting can be hard sometimes. That's where the Shnapsen Cheater, Pumpkin Eater comes in. It Counts the points for you and tells you to declare your voctory at the perfect time. You input pointt values with long and short presses (long press-10 points, short press-1 point) and it beeps at 50 points as a warning, and then at 66 for your win. You might be asking, what if my opponent catches me? Well I've got that covered. If you pull the Schnapsen Cheater, Pumpkin Eater out from under the table, the light sensor will detect it's being watched and its eyes will turn green to show how harmless it is. It also turns off the counting function off so there's no chance of you getting caught.  

The most important thing I learned were button debugging, value of a state based approach, and order of opperations. I ran into a lot of issues with my button given that I am sensatively measuring the length of the presses; the things that helped me the most were trying different configurations of pins, setting a minimum press time, and using serial monitor to check my values. The state based approach allowed me to work the light sensor and the button pressing into the code without them conflicting, and made it really easy to measure different button press lengths. My biggest mistake was the order I went through building my project. It would have bee much easier to sew in all of the traces before putting the plushy together. 

The only rescources I used were the lecture slides.

Final Material List: 

1 8.5"x11" sheet orange felt (divided in two for front and back)\
1 8.5"x11" sheet green felt (only ~1"x4" used)\
1 skein green embroidery floss\
1 skein orange embroidery floss\
1 bobbin conductive thread\
lilypad components:\
  arduino\
  2 green LEDs\
  light sensor\
  buzzer\
  battery\
  button

Paper Prototype:
![Paper_Prototype](https://fac2-ctrl.github.io/assets/img/final_paper.pdf){: .mx-auto.d-block :}
Alligator Prototype:
![Alligator_Prototype](https://fac2-ctrl.github.io/assets/img/final_alligator.jpeg){: .mx-auto.d-block :}
Final Project:
![light_on](https://fac2-ctrl.github.io/assets/img/final_on.jpeg){: .mx-auto.d-block :}
![light_off](https://fac2-ctrl.github.io/assets/img/final_off.jpeg){: .mx-auto.d-block :}
![it_beeps_i_promise](https://fac2-ctrl.github.io/assets/img/beeps.jpeg){: .mx-auto.d-block :}
