
git push -u origin master

- set upstram for git pull/status
- 기능 확인 하는 법 git push -help

6월 9일 오전 배운 내용
1. docker 서버에서 안쓰는 컨테이너 지우기
    ```bash
    $ cd newworld #[내가 지우고자하는 컨테이너]
    $ make rm
    $ make rmi
    ```

2. 다시 내가 만들고 싶은 컨테이너 생성하기
    ```bash
    $ cd newworld #[만들고자하는 컨테이너]
    $ make build
    $ make make run
    ```

3. Dockerfile 들어가서 추가하고 싶은 apt 설치하기
    ```
    # install
    RUN apt-get update
    RUN apt-get git 
    ```

4. 내가 만든 도커 컨테이너로 이동하기
    ```
    # Attach visual studio 눌러서 새로운 컨테이너창 열기
    ```

5. 내가 작성한 내용 깃으로 올리기
    ```bash
    $ git remote add origin https://github.com/szjung-test/mainpractice.git
    $ git pull origin master
    $ git add hello.html
    $ git commit -m "docker first commit"
    $ git push -u origin master
   ```

6. torch에서 랜덤시드값 고정하는법
    ```python 
    import torch
    torch.random.manual_seed(777)
    ```

7. 주석 꿀팁
    ```
    ctrl + /
    ```

6월 10일 배운 꿀팁

1. shift + Delete = 영구 삭제

2. Dockerfile 에 opencv 오류해결 apt
    ``` 
    RUN apt-get update && apt-get install -y sudo
    RUN apt-get install -y libgl1-mesa-glx
    ```

3. 기존 도커 컨테이너 삭제후 다시 생성
    ```bash
    make rm
    make rmi
    make build
    make run
    ```

3. newworld 컨테이너에서 업데이트
    ```
    pip install --upgrade pip
    pip install torch torchvision sklearn numpy seaborn opencv-python
    ```

컨테이너에 설정 다시 완료!

오늘 설치한 것
1. VirtualBox에 Ubuntu server 다운받고 Docker 설치

```bash
sudo apt-get update && upgrade
sudo apt-get install ca-certificates \ curl \ gnupg \ lsb-release

sudo apt install docker.io
sudo apt-get update
sudo docker version
sudo apt install net-tools
ifconfig
```

 6월 13일 꿀팁

 1. git pull origin master
 - origin이 원격저장소 이름이 되고 master 브랜치로 가져온다는 뜻

 2. ssh-keygen
 - ssh 키가 저장되는 디렉터리는 .ssh 디렉터리

    - id-rsa =  프라이빗키
    - id-rsa.pub = 퍼블릭키                       


 3. N/.ssh. 디렉터리는 홈 디렉터리 하위에 만들어짐

 4. git pull 원격 브랜치 정보가져오기

6월 14일 꿀팁

git branch 활용 관리법

[HEAD] 해당 브랜치의 마지막 커밋이 해당 부분

예시)
```bash
Toy Story@DESKTOP-O3V1LK3 MINGW64 ~/Documents/git-test (feat/b)
$ git log
commit 6a13f83171fa4a0af52170fb256cba034bb2c4f2 (HEAD -> main, origin/main, origin/HEAD)
Merge: 1b7fde2 36d7d66
Author: szjung-test <93111772+szjung-test@users.noreply.github.com>
Date:   Tue Jun 14 15:09:11 2022 +0900

    Merge pull request #1 from szjung-test/feature/comment

    댓글 기능 추가
```

checkout 은 브랜치를 이동하는 명령어

checkout -b
다른 브랜치 HEAD 추가하기

예시)
```
git checkout -b "feature-layout"
```

HEAD -> feature-layout, origin/main, origin/HEAD, main

```Toy Story@DESKTOP-O3V1LK3 MINGW64 ~/Documents/git-test (main)
$ git checkout -b "feature-layout"
Switched to a new branch 'feature-layout'

Toy Story@DESKTOP-O3V1LK3 MINGW64 ~/Documents/git-test (feature-layout)
$ git log
commit 6a13f83171fa4a0af52170fb256cba034bb2c4f2 (HEAD -> feature-layout, origin/main, origin/HEAD, main)
Merge: 1b7fde2 36d7d66
Author: szjung-test <93111772+szjung-test@users.noreply.github.com>
Date:   Tue Jun 14 15:09:11 2022 +0900

    Merge pull request #1 from szjung-test/feature/comment

    댓글 기능 추가
```
Merge 머지 
- 브랜치와 브랜치를 합치는 명령어

6월 15일 꿀팁
- [미리캔버스 URL] (https://www.miricanvas.com/).
 - 장점 : 미리캔버스를 이용하면 ppt를 이쁘게 만들수 있다.
 - 단점 : 아이콘 커서가 다 커서 세세하게 조정이 어렵다.

6월 16일 꿀팁
- git brach를 이용하면 버전 관리에 용이하다.

## DeepLearing by pytorch
 - Adam() 은 SGD의 변형 함수 이다.
 - nn.MSELoss() : 두 개의 같은 크기 행렬을 받아 각 자리의 차이에 제곱해서 평균 객체 생성 
 - criterion : (decoded - y)^2


6월 17일 꿀팁

- Classification : 입력으로 주어진 이미지 안에 어떤 object가 있는 지에 따라 class(label)을 구분하는 행위
- Localization : 이미지 안의 object가 어느 위치에 있는지 정보를 출력

- Semantic segmentation : classification + Localization

- Instance segmentation : 같은 class여도 서로 다른 instance들을 구분한다. 즉 object detection처럼 이뤄진다.
    - object segmentaion : 서로 다른 object가 섞여 있어도 찾을 수 있음, 사진에 보이는 해당 object 들을 각각 골라냄



출처 : https://velog.io/@cha-suyeon/%EB%94%A5%EB%9F%AC%EB%8B%9D-Object-Detection-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%9A%A9%EC%96%B4-%EC%A0%95%EB%A6%AC

6월 21일 꿀팁

- 브라우저에서 방금 닫은 페이지 복구 방법 : ctrl + shift + t
- 우클릭 불가능할 때 사용방법 : f12 , f1, setting :disable javascript 체크


6월 23일 꿀팁
- 딥러닝 분야별 State-of-the-art(SOTA) 확인 가능 사이트 [[site]](https://paperswithcode.com/sota?fbclid=IwAR16wLSr-BAcl-eZAwMVIHdsmpgBF6dN4ETR5kRGg02f_5xBBOlN6uMapo4)

- Pose Estimation 분야가 굉장히 요즘 각광 받는 분야
- 크게 Top-down 방식과 Botton-up 방식으로 크게 나뉨

6월 27일 꿀팁
### RNN
- RNN은 시계열 데이터의 정보를 받아 전체 내용을 학습한다.
- 순차적 데이터의 흐름을 모두 내포
- RNN은 시계열 데이터의 정보를 하나씩 입력받을 때마다 입력된 벡터들을 종합해 은닉 벡터를 만듬
- LSTM, GRU, language modeling, text sentiment analysis, machine translation

6월 28일 꿀팁
### CNN모델
- Conv - Activation - pool
- stride - 픽셀 움직이고 작게 압축 시킨다 
-  $N-F\over S$ + 1
- feature map - 컨볼루션 거친 이미지의 특징 추출
- Pooling -  필터가 지나갈 때마다 픽셀 묶음
    - 평균 풀링
    - 최댓값 풀링


### Alex-Net
- Conv - Normalize - Activation - Pool


6월 29일 꿀팁
- 응용 RNN
     - LSTM : 기울기 소실 문제 해결, sequential 데이터 처리
     - GRU : RNN 을 포함하는 신경망, 파이토치의 nn.Module 상속 받음

- RNN은 입력이 너무 길어지면 gradient explosion, vanishing gradient 발생
- 은닉벡터 정의 : __init__state()
- forward 함수 정의 : self.gru(배치사이즈, 입력 x 길이, 숨겨진 차원) 3d 텐서
- train, evaluate

6월 30일 꿀팁
- 인코더 : 원문의 내용을 학습하는 RNN, 원문의 뜻과 내용을 압축하여 문맥 벡터(context vector)
- 디코더 : 인코더의 내용 벡터 입력 받아 토큰들을 차례대로 예측

### adverdarial attack 적대적 공격
- 딥러닝 모델의 약점 발견

### GAN(Generative Adversarial Network) 생성적 적대 신경망
- 생성자(Generator)와 식별자(Discriminator)가 서로 경쟁하여 데이터를 생성하는 모델
- 생성자(Generator) :  생성된 z를 받아 실제 데이터와 비슷한 데이터를 만드는 학습
- 식별자(Discriminator) : 실제 데이터와 생성자가 가짜 데이터를 구별하도록 학습

### 신경망 스타일 트랜스퍼(Neural Style Transfer)
- 콘텐츠 이미지(C)
- 스타일 이미지(S)


7월 1일 꿀팁

### VGG모델 생성
- torchvisions.models 제공 사전 학습된 모델 사용
- 2개 모듈 구성
- 모든 컨볼루션 블록은 feature 모듈에 정의 전열결이나 선형레이어는 Classifier 모듈 정의
    - 컨텐츠 오차
    - 스타일 오차

### VGGNet 
- 3*3 작은 필터 모든 Conv 레이어 사용
- 작은 필터를 사용함으로 더 많은 ReLU함수 사용 가능, 더 많은 비선형성 확보

### 7월 4일
- 함수나 라이브러리를 더블클릭하고 F12 누르면 클래스가 선언된 부분을 확인 할 수 있음
- 라이브러리는 클래스로 이루어져있으므로 그 작동원리를 확인 할 수 있음
- opencl 병렬 컴퓨팅에 이용


### 7월 19일
- FastAPI main.py 실행 오류

```
szjung@esp:/workspace/newworld/FastAPI$ uvicorn main:app --reload
INFO:     Will watch for changes in these directories: ['/workspace/newworld/FastAPI']
ERROR:    [Errno 98] Address already in use
```

- 해결 방법 : 컨테이너에서 디폴트 포터가 이미 사용중이여서 안되기 때문에 
- uvicorn main:app --reload --host 0.0.0.0 --port 6565 이렇게 뒤에 안쓰는 포트 번호를 사용해준다.

### 7월 20일
- 도커 로그 확인하는 명령어
- 도커 make up 파일 실행하고 로그를 확인하고 싶을 때 쓰는 명령어
- docker logs -f --tail 30 apisz1(확인하고 싶은 컨테이너)

- iterm2 를 이용해서 FastAPI 폴더를 만들고 실습해본다.

### 7월 25일
- ssh 사용
- Django 는  MVT 모델이다.(Model, View, Template)
- Template = main.html (템플릿, HTML, CSS)
- View = views.py, urls.py
- url -> views.py -> templates / main.html

### 7월 26일
- Batch Normalization
    - Gradient vanishing/exploding 보완하기 위해 만들어짐
    - squash : sigmoid 이용
    - Training : mini batch 대신 moving averages
    - Higher learning rate : U 에 대해선 변화 없고, 오히려 gradient 감소
    - CNN에서 BN Input 더한다.
    - BN이 주는 효과 Local optimum 문제 발생 가능성 줄이는 효과
    - x,y 축 도메인을 [0,1] 범위로 변환하고 정규화를 한다.

### 7월 27일
- Django 스터디 꿀팁!
- 가상환경이 필요한 이유? : 여러 패키지들을 한데 모아서 관리하기 위해 사용
#### 1. Virtualenv
```
$ pip install virtualenv
```
- 설치후
```
$ virtualenv project_env
```
- 가상환경에 필요한 파일들이 현재 위치 아래의 project_env 라는 디렉토리 안에 설치 되는 식
- 만들어진 가상환경을 활성화하려면 activate 명령을 입력한다
```
$ source project_env/bin/activate
```
- 가상환경에서 빠져나오는법
```
deactivate
```

#### 2. venv
- 파이썬 3.4 부터는 venv라는 패키지가 기본으로 포함되어 있어서 따로 virtualenv 설치하지 않아도 가상환경 이용 가능
```
$ python -m venv project_env
```
- 가상환경 활성화 시키는 방법은 virtualenv 와 동일
```
$ project_env/scripts/activate
```

#### 3. 가상환경에서의 패키지 관리
- 로컬에서 가상환경을 활성화시키고 필요한 모든 패키지들이 설치되었으면, 어느 환경에서든 같은 패키지들이 한 묶음으로 설치
- requirements.txt 만들어 주는 것이 좋음
```
$ pip freeze > requirements.txt
```
- 원격 서버에서 이파일을 이용해 일괄 설치하는 방법
```
$ pip install -r requirements.txt
```

### Django 컴포넌트
- users
- other services
- web server
- URLS.py 
- Views
- models
- template

### Zen of python
- 파이썬이 추구하는 철학
```
python3
import this
```

### 프레임워크 VS 라이브러리
- 프레임워크
    - 내코드 > Django > Serving
    - 장고가 서빙의 주체 내코드를 불러서 장고에서 구현함
- 라이브러리
    - 라이브러리 > 내코드 > Serving
    - 내코드가 서빙의 주체 내코드를 라이브러리와 함께 구현함

### 7월 28일
- SRGAN 스터디
- 기존 PSNR과 MSE는 pixel wise image 차이 기반으로 정의 되어 있어서 high texture datail솨 같은 지각적(perceptual)차이를 잡는데 한계 존재
- But SR GAN 모델을 돌리고 MOS Test를 한 결과 ResNet보다 우수한 결과 도출

### 8월 1일
- 메타 데이터를 활용할 수 없는 4가지 일반적인 이유
1. 메타 데이터를 사전에 정의하면 시간이 많이 소요되고 배포하는 데도 오랜 시간이 걸린다.
2. 메타데이터는 필요한 만큼 유연하지 않다. (기존 메타데이터 모델은 변경하기 어렵고 비용이 많이 든다)

### 소프트웨어공학 4가지 중요 요소

1. 방법 - 계획수립과 추정, 시스템과 소프트웨어 분석, 자료구조, 프로그램 구조, 알고리즘, 코딩, 테스팅, 유지관리

2. 도구 - 어떤 일을 수행할 때 생산성 혹은 일관성을 목적으로 사용하는 방법들 (요구 관리 도구, 모델링 도구, 형상 관리도구, 변경 관리 도구)

3. 절차 - 방법과 도구를 결합하여, 소프트웨어를 합리적이고 적시에 개발할 수 있도록 함

4. 사람 - 소프트웨어공학에서는 많은 것(수립, 개선, 유지 등) 사람과 조직에 의해서 움직이기 때문에 사람에 대한 의존성이 상대적으로 큼

 

- 타당성 검토 → 개발 계획 → 요구사항 분석 → 설계 → 구현 → 테스트 → 운용 → 유지보수

 

▽나선형 모델

#### 특징 - 프로토타입을 지속적으로 발전시켜 최종 소프트웨어 개발까지 이르게 하는 점증적인 방법(Incremental development) 

- 위험관리가 중심인 생명주기 모델

 

▽점증적 개발(Incremental development)

- 점증적 개발은 계속 중간 버전들을 추가해 이전 버전에 기능을 더해가며 개발하는 방법

- 명세화(specification), 개발(development), 검증(validation) 동시에 진행된다는 특징

- 예를 들면 "웹을 만들 때 메인화면, 게시판, 로그인 화면 등이 필요하고 AWS를 사용할 것" 정도의 설명

 

### 수행단계 - 계획수립(Planning) → 위험분석(Risk Analysis) → 개발/구축(Engineering) → 고객평가(Evaluation)

 

- 나선형 모델은 Less Document oriented, 즉 문서를 통한 개발 방법

- 애자일 모델은 Code oriented  실질적인 코딩을 통한 개발 방법

 
- 나선형 모델은 프로젝트 수행 시 발생하는 위험을 관리하고 최소화 하려는 목적을 가진다.

- 애자일 모델은 품질의 저하 없이 변화를 수용하고 협업을 강조하고 '제품의 빠른 인도'를 강조하는 반복적 방법

 

- 요구사항 분석 단계 초점 : "어떻게(How to)"가 아니라 고객 관점의 "무엇(what)"에 맞춰져 있다.

- "무엇(what)=기획자"을 "어떻게(How to)" 만들 것인가 하는 개발의 문제와 일의 특성상 많은 차이가 있다.

- 요구사항 분석은 응용분야(Application) 관점에서 시스템이 무슨 기능을 수행해야 하는지 초점을 맞추어 시스템의 목표를 기술, 그 기능이 기술적(Engineering) 관점에서 어떻게 수행될 것인지는 기술하지 않음

 
- 요구사항 분류

- 요구사항은 크게 기능적 측면과 관리적 측면으로 분류, 일반적으로 기능적 측면의 요구사항 분류가 많이 활용

### 8월 2일
- Classification : 이미지를 분류하는 것으로 해당 이미지 내의 객체가 무엇인지 알려주는 것
- 분류 문제는 분류할 것인지 하나인지 여러가지인지에 따라 Single Label Classification, Multi Label Classification 나뉨
- 1) Single Label Classification: 분류해야할 객체가 여러 class 중 (3개 이상) 한 가지인 경우를 Single Label Classification 혹은 Multi Class Classification
- 2) Multi Label Classification: 분류해야할 객체가 여러 class 중 한 가지 이상인 경우 Multi Label Classification

- Object Detection : 이미지나 영상 객체(Objects)가 무엇인지 분류하고 객체의 위치까지 인식해주는 기술로 분류와 위치인식이 동시에 가능
- 사용하는 ML 프레임워크 : Tensorflow, Pytorch
- zero-shot learning: 처음보는 데이터를 분류 가능하도록 학습하는 것

### 8월 3일
- 컴퓨터 꿀팁
    - 실수로 창 닫았을 때
    - window : ctrl + shift + t
    - mac : command + shift + t
- SCP란?
- ssh 원격 접속 프로토콜 기반으로 한 SecureCopy(scp)의 약자로서 원격지에 있는 파일과 디렉터리를 보내거나 가져올때 사용하는 파일 전송 프로토콜이다.
- 1. 단일 파일 원격지로 보낼때
    - 구문: #scp[옵션][파일명][원격지_id]@[원격지_ip]:[받는위치]
    - 예시: #scp testfile2root@192.168.159.129:/tmp/testclient

- 2. 복수의 파일을 원격지로 보낼때
    - 구문: #scp[옵션][파일명1][파일명2][원격지_id]@[원격지_ip]:[받는위치]
    - 예시: #scp testfile1 testfile2 root@192.168.159.129:/tmp/testclient

- 3. 여러 파일을 포함하고 있는 디렉터리를 원격지로 보낼때(-r옵션 사용)
    - 구문: #scp[옵션][디렉토리이름][원격지_id]@[원격지_ip]:[보낼경로]
    - 예시: #scp -r testgo root@192.168.159.129:/tmp/testclient
