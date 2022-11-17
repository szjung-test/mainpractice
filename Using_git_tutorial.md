1. 원격 저장소에서 로컬 저장소로 가져오기
```
로컬에 파일 없을 때 : git clone http://~~~
로컬에 파일 있을 때 : git pull origin master
```


2. 로컬 저장소에서 작업할 브랜치를 생성 후 해당 브랜치로 이동
```
git barnch 브랜치명     // 브랜치 생성
git checkout  브랜치명  // 브랜치 이동
동시에 명령 : git checkout -b 브랜치명
```

3. 브랜치 안에서 원하는 작업 수행

4. 브랜치 안에서 수행한 작업 git에 올림
```
git add .
git commit -m "커밋내용"
원격 저장소에 해당 브랜치 존재시: git push
원격 저장소에 해당 브랜치 없을때: git push origin 브랜치명
```

5. 로컬 master 브랜치로 이동 후 원격 저장소의 master 변경사항을 pull 하기
```
작업중인 브랜치 안에서 명령어 실행 : git checkout main
master  브랜치 안에서 명령어 실행 : git pull origin master
```

6. 다시 작업한 브랜치로 이동하고 로컬 master 내용을 해당 브랜치에 merge
```
git merge master
git push
```


7. github repository에서 pull request 요청하면 완료

8. 담당자가 확인 후 pull request 수락하면 원격 저장소 master에 브랜치 내용이 업데이트 완료
