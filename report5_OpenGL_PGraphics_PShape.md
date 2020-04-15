컴퓨터그래픽스
===========
#### 과제5: OpenGL, PGraphics, PShape에 대해 알아보고, 예제 실습해보기


-------------

 ## OpenGL

OpenGL의 정의 및 응용 

Open Graphics Library의 약자로, 1992년 실리콘 그래픽스사에서 만든 2차원 및 3차원 그래픽스 표준 API규격으로, 프로그래밍 언어 간 플랫폼 간의 교차 응용 프로그래밍을 할 수 있도록 설계되었습니다. 이 API는 약 250여개 가량의 함수 호출을 이용하여 여러가지 기능을 지원합니다. 
OpenGL은 Direct3D와 OpenGL은 컴퓨터 그래픽 세계에서의 핵심입니다. 대표적으로 CAD, 가상현실, 정보시각화, 비행 시뮬레이션 등의 분야에서 활용되고 있고, 컴퓨터 게임 분야에서도 널리 활용되고 있습니다. OpenGL을 사용하여 개발된 게임 중에는 이드 소프트웨어의 퀘이크, 둠3 시리즈가 있습니다. 또한 JAVA를 이용하여 개발된 게임 룬스케이프와, 언리얼 등이 있습니다.  


-------------
## PGraphics 예제 변경하기

PGraphics 의 예제 중 Create Graphics을 선택하여 변형하였습니다. 

#### 1. 변경점
전체적인 화면 크기와, PGraphics의 크기를 조정하였습니다.     
원의 개수를 2개 더 추가하였고, 크기를 본래 원 보다 작게하여, 물 분자와 비슷한 모양을 만들었습니다.
random()을 사용하여 원들의 색깔이 시간에 따라 바뀌도록 하였습니다.   
PGraphics의 화면 안에 마우스 커서가 들어가면 "반가워요!" 라는 텍스트가 출력되도록 변경하였습니다.    


#### 2. 소스코드
```
PGraphics pg;
PImage bg;
PFont f;
float i,j,k;
float tc=random(0,255);

void setup() {
  size(840, 700);
  pg = createGraphics(400, 400);
textSize(72); 
f = createFont("굴림",64);
textFont(f);
}

void draw() {

  fill(0, 20);
  rect(0, 0, width, height);
  fill(255);
 
  noStroke();
if(i>255&&k>255&&j>255){
i=random(0,255);
j=random(0,255);
k=random(0,255);}
else j=j+0.7; i=i+0.9; k=k+0.6;
  fill(j,k,i);
   ellipse(mouseX, mouseY, 60,60);
   fill(k,j,i);
  ellipse(mouseX+20, mouseY+15, 30, 30);
  fill(i,j,k);
  ellipse(mouseX-20, mouseY-15, 30, 30);
    
    
  
  pg.beginDraw();
  pg.background(51);
  pg.noFill();
  pg.text("반가워요!",mouseX-200,mouseY-130);
  if(mousePressed){
 
  f = createFont("굴림",64);

 pg.text("반가워요!",mouseX-200,mouseY-130);
}
  /*pg.stroke(255);
  pg.ellipse(mouseX-200, mouseY-130, 90, 90);
    pg.ellipse(mouseX-200, mouseY-130, 60, 60);
      pg.ellipse(mouseX-200, mouseY-130, 30, 30);
  */
  pg.endDraw();

  // Draw the offscreen buffer to the screen with image() 
  image(pg, 200, 130);

   
}
```

##  PShape 예제 변경하기
 PShape의 예제 중 Custom PShapes을 변형하였습니다.
 
 #### 1. 변경점
 background를 void setup()의 영역으로 이동하여 background 생성의 반복을 멈추어 별이 생성될 때 마다 화면에 누적되도록 하였습니다.  
 생성되는 별의 색깔이 다양하게 출력되도록 변경하였습니다. 단, 범위가 한정되어 있기 때문에 별의 색은 한정된 범위 안에서 출력됩니다.  
 기울기를 줘서, 별이 출력될 때 각각 다른 각도를 가지도록 하였습니다.  
 키보드로부터 값을 입력받아 delay를 이용해 별이 출력되는 스피드를 조절할 수 있도록 하였습니다.  
 #### 2. 소스코드

```
int sp;
float f;
void setup(){
size(1000,1500); 
background(255);
}

 int c,c1, c2;
void draw()
{
  
   if(mousePressed == true){
   
  float a= random(0,100);
float b=random(0,100);
translate(mouseX-a,mouseY-b);
  strokeWeight(1);
  fill(c,c1,c2);
  rotate(tan(f));
  f=f+0.01;
  beginShape();
  vertex(0, -50);
  vertex(14, -20);
  vertex(47, -15);
  vertex(23, 7);
  vertex(29, 40);
  vertex(0, 25);
  vertex(-29, 40);
  vertex(-23, 7);
  vertex(-47, -15);
  vertex(-14, -20);
  endShape(CLOSE);
delay(sp*10);
c=c+2;
c1=c1+3;
c2=c2+4;
if(c>255)c=0;
if(c1>255) c1=0;
if (c2>255) c2=0;

}}
  

void keyPressed(){

sp = key-'0'; 

}
```

## 작성소감

이번 변형과제를 하며, 여러가지를 시도해 보기 위해서 인터넷에 검색도 해보고, 수업카페에서 자료도 찾아보면서 적용해보았습니다. 제가 계획한 대로 잘 적용이 될 때도, 그렇지 못할 때도 있었습니다. 이번 프로젝트에 제가 원하는 대로 코드를 적용하진 못 했지만 이렇게 실패하는 과정 속에서도 배움이 있다는 것을 알았습니다. 왜 프로그램이 생각한대로 작동하지 않는지 고민하며, 그에대해 더 깊이 탐구하고 이해하는 시간을 가졌습니다. 또, 인터넷에 검색을 하다보면 프로세싱에 대한 다양한 정보를 얻고, 이것들을 어디에 어떻게 쓰면 좋을지 머릿속에 구상이 됩니다. 아직까지는 실력이 좋지 못해 큰 틀을 잡는 것 밖에 하지 못하지만, 프로세싱을 배우면 배울수록 조금씩 세부적인 부분도 눈에 들어오는 것 같습니다. 점점 머릿 속에 지식이 쌓이는 것 같아 즐겁습니다. 계속 쌓아가면 언젠간은 제가 하고싶은 모든 것들을 할 수 있게 될 거라 생각합니다. 감사합니다! 
덧붙여서, 교수님이 강의 때 말씀하셨던 별 회전은 sin()이 아닌 tan()을 사용하면 정방향으로 돌아갑니다! 제 생각에는 sin의 그래프가 연속되는 모양이라서 +각도에서 -긱도로, -각도에서 +각도로 회전하는 것 같습니다. tan은 그래프가 -각도에서 +각도로, 그 다음 다시 -각도에서 +각도로 그려져서 별의 회전에 적용하면 계속 같은 방향으로 돌아가는 모습을 볼 수 있습니다.  
