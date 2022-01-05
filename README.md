라즈베리파이4에 OpenCV 설치하고 얼굴인식하기

프로파일
 오픈랩 ・ 2021. 5. 19. 9:46
URL 복사  이웃추가 
라즈베리파이 운영체제를 설치한 후 OpenCV 4.1을 설치해보겠습니다. 


먼저, 라즈베리파이 운영체제는 다음의 링크에서 다운로드 받고, 설치합니다. 

[설치](https://www.raspberrypi.org/software/raspberry-pi-desktop/)


필요한 준비물

1. 라즈베리파이 4 4GB

2. MicroSD카드 (운영체제가 업로드될 공간)

3. SD카드 리더기 (PC에서 운영체제를 SD카드에 설치할 때 필요)

4. HDMI케이블 (PC와 잠시 연결할 목적으로 HDMI 케이블)

5. 웹캠 (얼굴 인식 예제 구현)

​

​

라즈베리파이 설치하기

라즈베리파이를 설치와 관련하여 기본적인 가이드는 다음의 PDF를 참고해주세요. 

https://cafe.naver.com/mechawiki/4527


운영체제를 설치하고, 라즈베리파이를 부팅한 후에는 버전 체크를 해봅니다. 

​

​

라즈베리파이 버전 체크

pi@raspberrypi:~ $cat /etc/os-release
PRETTY_NAME="Raspbian GNU/Linux 10 (buster)"

NAME="Raspbian GNU/Linux"

VERSION_ID="10"

VERSION="10 (buster)"

VERSION_CODENAME=buster

ID=raspbian

ID_LIKE=debian

HOME_URL="http://www.raspbian.org/"

SUPPORT_URL="http://www.raspbian.org/RaspbianForums"

BUG_REPORT_URL="http://www.raspbian.org/RaspbianBugs"

​

제 라즈베리파이 운영체제의 버전은 10(buster)라고 합니다. 

​

​

VNC를 활용하여 원격으로 라즈베리파이 접속하기

라즈베리파이에 운영체제가 설치된 후에는 VNC를 이용하여 원격 접속이 가능합니다. 

VNC로 원격 접속하기는 예전에 올린 블로그를 참고해주세요

https://blog.naver.com/roboholic84/221024014008


라즈베리파이 원격모니터링 VNC
SSH를 사용하게 되면, 터미널 위주의 작업이다보니 디스플레이 및 영상 관련 프로그래밍의 결과를 확인...

blog.naver.com

​

OpenCV 설치

OpenCV는 Open Computer Vision으로 

오픈소스화된 컴퓨터 비전처리 라이브러리입니다. 

아마 컴퓨터로 영상처리를 한다면, 

가장 많이 사용되는 라이브러리라고 볼 수 있습니다. 

거의 필수입니다. 

​

OpenCV 설치하기는 많은 예제들이 있고, 

직접 설치해보면서 검증된 링크를 소개합니다.

​

https://qengineering.eu/install-opencv-4.1-on-raspberry-pi-4.html


Install OpenCV 4.1 on Raspberry Pi 4 - Q-engineering
A thorough guide on how to install OpenCV 4.1.2 on your Raspberry Pi 4 with CMake

qengineering.eu

하나씩 따라하다보면 1시간 정도 걸리는 것 같습니다. 

​

이제 본격적으로 OpenCV를 사용해보죠.

​

OpenCV 샘플 예제 실행시켜보기

OpenCV를 설치한 후에 웹캠을 USB에 연결해줍니다. 

그리고, 터미널 창을 열고 OpenCV의 샘플 파일로 접근합니다. 

터미널은 왼쪽 상단의 폴더 오른쪽의 검정색 아이콘을 클릭하면 열립니다. 

ls(엘에스)라는 명령어를 넣으면 해당 위치에서의 폴더와 파일을 볼 수 있습니다. 


그 다음에는 cd opencv를 입력해서 opencv 폴더로 이동하고, 다시 ls를 입력해서 내부를 봅니다. 


samples라는 폴더로 이동하기 위해 다시 cd samples를 입력하고 ls를 입력해서 내부 폴더와 파일을 보죠. 

python이라는 폴더가 있습니다. 

그 외에도 cpp라는 폴더, java라는 폴더도 있는데 언어에 따른 샘플들을 가지고 있습니다. 

뭔가 opencv 놀이터 같은 느낌이죠?

​


확장자가 모두 py로 되어 있다는 것은 모두 파이썬 파일이라는 말입니다. 

그 중에서 facedetect.py를 실행해볼께요. 

​

우리가 사용하는 파이썬은 버전 3라서 파일을 실행하기 위해서는 "python3 [파일명]"을 입력합니다. 

python3 facedetect.py를 입력해볼께요. 

​

마스크를 쓰고 있을 때는 얼굴 인식을 하기 어렵다는 것을 느낍니다. 

거의 인식이 안되네요. 

​



​

그 이유에 대해서는 다음 시간에 포스팅하고, 

텐서플로를 통한 인식 개선을 다뤄볼께요. 
