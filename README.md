
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
브랜치와 브랜치를 합치는 명령어
