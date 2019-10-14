/*# LINE-FOLLOWER-ROBOT-CODE-USING-TWO-IR-SENSORS-
This is the code for Line Follower Robot that can work using two IIR SENSORS. This code works with the help of Arduino. The Arduino Board used in this LFR is Arduino UNO.  Please keep a check of the pin mode numbers that you use in  your LFR to connect to the Motors and the IR SENSORS. Make the necessary changes accordingly.*/ 

int leftsensor = 10;
int rightsensor =11;

int rightmotor1 = 6;
int rightmotor2 = 7;

int leftmotor1 =8;
int leftmotor2 =9;

void setup() {
  
  pinMode(rightmotor1, OUTPUT);
  pinMode(rightmotor2,OUTPUT);
  
  pinMode(leftmotor1, OUTPUT);
  pinMode(leftmotor2, OUTPUT);
  
  pinMode(leftsensor,INPUT);
  pinMode(rightsensor,INPUT);


  pinMode(3, OUTPUT);
  pinMode(3 , HIGH);
}

void loop() {

 while((digitalRead(leftsensor)==LOW)&&(digitalRead(rightsensor)==LOW))
    {  brake();
    }

 while((digitalRead(leftsensor)==LOW)&&(digitalRead(rightsensor)==HIGH))
  { left();
    }

 while((digitalRead(leftsensor)==HIGH)&&(digitalRead(rightsensor)==LOW))
  { right();
    }

 while((digitalRead(leftsensor)==HIGH)&&(digitalRead(rightsensor)==HIGH))
  { forward();
    }
}

void brake()
{ digitalWrite(rightmotor1,LOW);
  digitalWrite(rightmotor2,LOW);
  digitalWrite(leftmotor1,LOW);
  digitalWrite(leftmotor2,LOW);
  }

  void left()
{ digitalWrite(rightmotor1,HIGH);
  digitalWrite(rightmotor2,LOW);
  digitalWrite(leftmotor1,LOW);
  digitalWrite(leftmotor2,LOW);
  }

  void right()
{ digitalWrite(rightmotor1,LOW);
  digitalWrite(rightmotor2,LOW);
  digitalWrite(leftmotor1,HIGH);
  digitalWrite(leftmotor2,LOW);
  }


  void forward()
{ digitalWrite(rightmotor1,HIGH);
  digitalWrite(rightmotor2,LOW);
  digitalWrite(leftmotor1,HIGH);
  digitalWrite(leftmotor2,LOW);
  }
