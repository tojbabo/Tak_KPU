# OJJJ
개인 공부 공간


<ctrl +f>로 <branch name>을 찾아서 확인하세요

-----------------------------------------------------------------HI-----------------------------------------------------------------

--------------------------------------------------------------SERVER--------------------------------------------------------------

목적 - 캠으로 촬영된 영상을 서버로 전송했다가 다시 수신해서 출력하기
       서버는 AWS ec2 ubuntu.
       
~~~~~~ - <tcp_Server ver1.0.c> / <Client ver Python 1.0.py> / Client ver C++ 1.0.cpp> / <Header to Client C++ 1.0.h>

190703 - 캠으로 촬영된 영상의 순간 프레임을 서버로 전송하기 위해서는 데이터의 변환이 필요. 
         Mat(프레임)을 uchar*(변환된 형태)로 변환은 기본 제공해줌.
         서버로 전송및 수신하기 위해선 char형 배열 또는 포인터로 다루어야 할 것 같음.
       
       1) uchar* -> char* 변화시 데이터 손실 없음을 확인. 
       2) char*형태로 서버 데이터 송신 가능 확인.
       3) Mat -> uchar* -> char*(송신) -> char*(수신) -> uchar* -> Mat -> 출력.
       4) 문제 없이 작동함을 확인. 딜레이는 약 0.16 ~ 0.17 사이
       < udp_Server ver 1.0.c> / < Client C++ ver 1.1.cpp >
