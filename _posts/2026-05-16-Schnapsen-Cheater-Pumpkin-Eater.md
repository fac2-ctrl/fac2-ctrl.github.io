---
layout: post
title: Final Project: Schnapsen Cheater, Pumpkin Eater!
author: Felix Crary
---

Hi Everyone! Here's my final project for the semester: the Schnapsen Cheater, Pumpkin Eater! I really love the card game Schnapsen, and one of the main functions of the game is that the player has to count their own points. Once the player gets to 66 points they must declare their victory or it doesn't count. But ya'know counting can be hard sometimes. That's where the Shnapsen Cheater, Pumpkin Eater comes in. It Counts the points for you and tells you to declare your voctory at the perfect time. You input pointt values with long and short presses (long press-10 points, short press-1 point) and it beeps at 50 points as a warning, and then at 66 for your win. You might be asking, what if my opponent catches me? Well I've got that covered. If you pull the Schnapsen Cheater, Pumpkin Eater out from under the table, the light sensor will detect it's being watched and its eyes will turn green to show how harmless it is. It also turns off the counting function off so there's no chance of you getting caught.  

code:
```arduino
// PINS
int SENSOR = A4;
int pinHigh = A5;
int LED = 6;
int BUTTON = A3;
int BUZZER = 10;

// light sensor
int dark = 200;
int sensor;

// button vars
bool buttonState = false;
bool lastButtonState = false;
int pressTimer = 0;

// point counting
int points = 0;
bool warningToggle = true;
int warning = 50;

int interval = 50;
long timer = 0;

void setup() {
  pinMode(SENSOR, INPUT);
  pinMode(BUTTON, INPUT);
  pinMode(LED, OUTPUT);
  pinMode(BUZZER, OUTPUT);
  pinMode(pinHigh, OUTPUT);
  digitalWrite(BUTTON, HIGH);
  digitalWrite(pinHigh, HIGH);
}

void loop() {

  sensor = analogRead(SENSOR);
  buttonState = digitalRead(BUTTON);

  // light sensor
  if (sensor > dark) {
    digitalWrite(LED, HIGH);
  } else {
    digitalWrite(LED, LOW);

    //button
    if (buttonState == LOW) {
      pressTimer += interval;
    }
    if (buttonState == HIGH && lastButtonState == LOW) {

      if (pressTimer > 1500) {
        points = 0;
        warningToggle = true;
      } else if (pressTimer > 400) {
        points += 10;
      } else if (pressTimer > 50) {
        points += 1;
      }

      pressTimer = 0;
    }

    // buzzer
    if (points >= warning && warningToggle) {
      tone(BUZZER, 440);
      warningToggle = false;
    } else if (points >= 66) {
      tone(BUZZER, 880);
      points = 0;
    } else {
      noTone(BUZZER);
    } 

    delay(interval);
    timer += interval;
    lastButtonState = buttonState;
  }
}

```


![Paper_Prototype](https://fac2-ctrl.github.io/assets/img/IMG_9790.jpeg){: .mx-auto.d-block :}
![Alligator_Prototype](https://fac2-ctrl.github.io/assets/img/IMG_9790.jpeg){: .mx-auto.d-block :}
![light_on](https://fac2-ctrl.github.io/assets/img/IMG_9790.jpeg){: .mx-auto.d-block :}
![light_off](https://fac2-ctrl.github.io/assets/img/IMG_9790.jpeg){: .mx-auto.d-block :}
![it_beeps_i_promise](https://fac2-ctrl.github.io/assets/img/IMG_9790.jpeg){: .mx-auto.d-block :}
