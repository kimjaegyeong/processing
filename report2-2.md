**한글 배너를 제작하시오.**

 

`1. "안동대 컴공 사랑합니다"`

`2. 위에서 아래로 내려오도록 배너를 만드시오.`

`3. 키보드로 속도를 0~9배까지 조절하도록 하시오.`

PFont f;  
void setup(){  
size(800,300);  
textSize(72);  
f = createFont("굴림",64);  
textFont(f);  
}  

int i=1,sp;  
void draw(){  
fill(0);  
background(255,50,255);  
text("안동대 컴공 사랑합니다",10,i);  
i=i+1*sp;  
if(i>300) i=1;  
}  
  
void keyPressed(){  
  
  sp=key-'0';}  
