컴퓨터그래픽스
=============
과제3 : Processing Example중 한 가지를 골라 변형하기   



1 Example 선택 
-------------
##### Processing Example중, Bouncing Ball을 선택하였습니다.

2 Bouncing Ball 
-------------
##### Bouncing Ball은 좌우로 이동하며 바닥에 부딪히면 위로 튀어 오르는 공을 생성합니다.

3 Bouncing Ball 변형 결과
-------------
##### 공이 튀어 오르고 바닥에 부딪힐 때 마다 공의 위치에너지가 줄어들어 점점 공의 위치가 바닥과 가까워집니다. 마우스로 화면을 클릭하면 공이 튀어 오르는 힘이 더 강해집니다. 단 바닥과 가까워진 상태의 공은 마우스 연속클릭을 하여, 튀어 오르는 힘을 더 키워줘야 합니다. 공이 너무 높게 튀어 올라 화면 밖으로 나갔을 때는 아래에서 공이 튀어나옵니다.

4 작성소감 
-------------
##### processing이 기본적으로 지원 해주는 기능과, Example이 많아서 다른 언어를 공부할 때 보다 더 쉽게 느껴집니다. 또한 processing은 도형이나 선, 트리 등등 다양한 그래픽을 구현할 수 있어서 다른 언어로 코딩하는 것보다 더 흥미 있고, Example을 변형하여 만들 수 있는 프로그램들이 많이 떠올랐습니다. 마우스로 공을 당겨서 튀어 오르게 하는 건 어떻게 하지? 스프링을 추가해서 스프링이 작동하면 공이 튀어 오르도록 할 수 있는 방법은 없을까?라고 스스로 의문점을 제시하며 해결책을 찾으려 온갖 코드를 바꿔보고, 실행해보는 활동을 반복하다보니 어느새 제가 사용하고 있는 코드들을 이해하기 시작한 것 같습니다. 또. 프로그램을 어떻게 하면 만들 수 있을까? 하며 고민하기 시작하니, 단순히 예제를 실습하는 동안에 생각했던 것보다 더 많은 것을 고려하게 되었습니다. 아직 부족한 실력이라 제가 만들고 싶은 것들을 다 구현해낼 수는 없지만, 더 열심히 배우고, 열정적으로 공부하여 제가 만들고자 하는 프로그램을 구현하는 것이 이번 학기 동안의 목표입니다.
   
     
     
###### 소스코드
```
PVector location;  
PVector velocity;  
PVector gravity;   

void setup() {
  size(640,600);
  location = new PVector(100,100);
  velocity = new PVector(3,8.1);
  gravity = new PVector(0,0.3);

}

void draw() {
  background(0);
  
 
  location.add(velocity);
 
  velocity.add(gravity);
  

  if ((location.x > width) || (location.x < 0)) {
    velocity.x = velocity.x * -1;
  }
  if( (location.y > height)|| (location.y <0)) {
   
    velocity.y = velocity.y * -0.7; 
    location.y = height;
  }

 
  stroke(255);
  strokeWeight(2);
  fill(127);
  ellipse(location.x,location.y,48,48);
}
void mousePressed(){
  velocity.y = velocity.y*1.5;
  
  
}
```
