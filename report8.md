컴퓨터그래픽스
=============

### 과제8 : 텍스쳐 매핑하기

------------------------------------------

##### 1. 소스코드
```
PImage tex;
float rotx = PI/4;
float roty = PI/4;

void setup() {
  size(640, 360, P3D);
  tex = loadImage("o9o9.png");
  textureMode(NORMAL);
  fill(255);
  stroke(color(44,48,32));
}

void draw() {
  background(0);
  noStroke();
  translate(width/2.0, height/2.0, -100);
  rotateX(rotx);
  rotateY(roty);
  scale(170);
  TexturedCube(tex);
}

void TexturedCube(PImage tex) {
  beginShape(QUADS);
  texture(tex);


  vertex(-1, -1,  1, 0, 0);
  vertex( 1, -1,  1, 1, 0);
  vertex( 1,  1,  1, 1, 1);
  vertex(-1,  1,  1, 0, 1);

  vertex( 1, -1, -1, 0, 0);
  vertex(-1, -1, -1, 1, 0);
  vertex(-1,  1, -1, 1, 1);
  vertex( 1,  1, -1, 0, 1);

  vertex(-1,  1,  1, 0, 0);
  vertex( 1,  1,  1, 1, 0);
  vertex( 1,  1, -1, 1, 1);
  vertex(-1,  1, -1, 0, 1);

  vertex(-1, -1, -1, 0, 0);
  vertex( 1, -1, -1, 1, 0);
  vertex( 1, -1,  1, 1, 1);
  vertex(-1, -1,  1, 0, 1);

  vertex( 1, -1,  1, 0, 0);
  vertex( 1, -1, -1, 1, 0);
  vertex( 1,  1, -1, 1, 1);
  vertex( 1,  1,  1, 0, 1);

  vertex(-1, -1, -1, 0, 0);
  vertex(-1, -1,  1, 1, 0);
  vertex(-1,  1,  1, 1, 1);
  vertex(-1,  1, -1, 0, 1);

  endShape();
}

void mouseDragged() {
  float rate = 0.01;
  rotx += (pmouseY-mouseY) * rate;
  roty += (mouseX-pmouseX) * rate;
}
```
-----------------------------------------
#### 2. 실행화면 

![1](https://user-images.githubusercontent.com/50646904/81043207-cd89af00-8eec-11ea-861a-d5727363d515.PNG)

------------------------------------------
#### 3. 소감

예전에 메이플스토리2라는 게임을 즐겨했었습니다. 그 게임은 사용자가 건축을 할 수 있도록 설계된 시스템이 있었는데, 이번에 실습했던 것처럼 사각형에 각종 텍스쳐가 씌인 박스를 이리저리 배치하며 건축을 할 수 있었습니다. 이번 텍스쳐 매핑을 실습하면서 그때 즐겼던 게임이 이러한 원리로 제작되었으리라고 짐작했습니다. 그렇다면 이러한 박스를 여러 개 만들고, 특정한 좌표에 배치할 수 있도록 하면 그때 했던 게임처럼 네모로 만들어진 건축물을 만들 수 있지 않을까? 라는 생각이 들었습니다. 그래픽스 자체가 굉장히 직관성이 좋아서 배우면 배울수록 활용할 수 있는 분야, 활용되고 있는 분야를 찾고 또 어떻게 적용시키면, 어떻게 프로그램을 짜면 내가 구상한 프로그램을 만들 수 있을까? 하며 생각하게 되는 것 같습니다. 머릿속에  아이디어들을 실현하게 되는 그 날까지 열심히 배우겠습니다. 언제나 감사합니다. 
