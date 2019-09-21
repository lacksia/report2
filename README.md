# 시나리오 및 작성 소감
시나리오 : 현재 자신의 집에 있는 반려 동물이 생활하기에 적합한 밝기인지 집 밖에서 그림으로 
쉽게 알 수 있다.
소감 : 그냥 가르쳐 주시는대로 듣고 따라하다가 일상생활에서도 쓰이고 있는 쓰임새에 대해서 배우고 나서 이러한 기능을 어떤 곳에서 쓸 수 있을지 상상하게 돼었습니다.
아두이노에 대해서 좀 더 관심이 생겼습니다.
밑줄 친 부분에 대해서는 조금만 더 설명을 해주시면 감사하겠습니다.
# 아두이노 코드
void setup() {
  Serial.begin(9600);
}
int a;  
void loop() {
  a=analogRead(A0);
  Serial.println(++a);
  delay(500);
}
# 프로세싱 코드
import processing.serial.*;
Serial p;
void setup(){
  size(300,300);
  p=new Serial(this,"COM4",9600);
}
void draw(){
  if(p.available()>0){
    String m=p.readString();
    int a= int (m.trim());
    println(a);
    if(a<100)         fill(250,0,0);
       if(100<a&&a<200) fill(0,250,0);
    if(200<a)         fill(0,0,250);
    ellipse(150,150,200 ,200);
  }
}
