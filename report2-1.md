**프로세싱으로 "Graphics"라는 배너를 만드시오.**

`1. 배너가 왼쪽 오른쪽으로 왔다 갔다 한다.`

`2. 키보드 0~9를 입력하면 속도가 조절이 된다.`

`3. 배경과 글자색을 본인이 좋아하는 색상으로 하시오.`   


**소스코드**

void setup() {

size(800, 300);

textSize(100);

}

int i, dir=1,sp=1;

void draw() {  
fill(0,255,0);  
 background(0,190,160);  
 text("Graphics", i, 200);  
 if(i>width) dir=-1;  
 if(i<0) dir=1;  
 i = i+dir*sp;  
}  
  void keyPressed(){  

sp = key-'0'; } 

**응용**  
`공의 좌우 왕복`  
void setup() {  

size(400 ,400);  
  
}  

int i, dir=1;  
 
void draw() {   
  
  background(0,190,160);  
  
  ellipse(i,200 ,80 ,80);   
fill(0,0,0);     

 if(i>width) dir=-1;     
 if(i<0) dir=1;                
 i = i+dir;            
}     
