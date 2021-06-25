## branch command

- 브랜치 생성

  ``` bash
  $ git branch 브랜치명
  ```

  

- 브랜치 목록

  ``` bash
  $ git branch
  ```

  

- 브랜치 이동

  ``` bash
  $ git checkout 브랜치명
  (브랜치명) $
  
  # git checkout 까지만 입력한 상태해서
  #tab 2번 누르면 checkout 가능한 브랜치명 확인 가능
  
  $ git checkout -b logout
  # branch 생성하면서 바로 입장
  ```

  ``` bash
  $ git log --oneline
  3ca75d1 (HEAD -> main) create master.py
  0d5a2a2 (origin/main) pull 내용 업데이트
  c29ad66 Create README.md
  17d72fd upload all data
  b0cc8dd 2021-06-24
  
  ```

  - head : 우리가 속한 위치

  ``` bash
  git log --all --graph --oneline
  ```

  

- 브랜치 생성 + 이동

  ``` bash
  $ git checkout -b 브랜치명
  ```

  

- 브랜치 병합

  ``` bash
  (master) $ git merge 브랜치 명
  ```

- 브랜치 삭제

  ``` bash
  $ git branch -d 브랜치명
  ```

  

- 브랜치 강제 삭제

  ``` bash
  $ git branch -D 브랜치명
  ```

  merge 가 되지 않은 브랜치는 강제로 삭제해야 함.



## 3가지 병합 상황

### 1. fast-foward

"다른 브랜치를 생성 한 후, master 브랜치에 변경사항이 없을 때"



### 2. 3-way Merge

"현재 브랜치(main)가 가르키는 커밋이 merge 할 브랜치의 조상이 아니라면 현재 브랜치와 merge할 브랜치의 커밋 2개와 두 브랜치의 공통조상 하나를 사용한다."



##### 1. 새로운 브랜치 signup 생성

##### 2. signup 브랜치에서 signup.py 생성

- git add.commit 잊지말기

##### 3. master 브랜치에서 new folder 생성

##### 4. master 브랜치와 sign 브랜치 병합





## Merge Conflict

"두개의 브랜치가 동일한 파일의 동일한 위치를 수정하고 merge하려고 할 때 발생하는 현상"

"단, 동일 파일을 수정했다고 하더라도 서로 다른 영역을 수정한다면 merge conflict는 발생하지 않음"

- git 이 자동으로 병합하지 못하는 상황 

  

#####  

1. 새로운 브랜치 hotfix 생성

   ``` bash
   $ git bash hotfix
   $ git checkout hotfix
   # git checkout -b hotfix
   ```

   

2. hot fix 브랜치에서 b.txt에 새로운 내용 입력

   - git add, commit

     ``` bash
     #b.txt에 아무거나 입력 후
     $ git add . or b.txt
     $ git commit -m "message"
     ```

     

     

3. master 브랜치에서 b.txt에 새로운 내용 입력

   - git add, commit

     ``` bash
     $ git checkout main(master)
     #아무거나 b.txt에 입력
     $ git add . or b.txt
     $ git commit -m "message"
     ```

     

4. master 브랜치와 hotfix 브랜치 병합

   ``` bash
   $ git merge hotfix
   # 결과값
   AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy (main)
   $ git merge hotfix
   Auto-merging b.txt
   CONFLICT (content): Merge conflict in b.txt
   Automatic merge failed; fix conflicts and then commit the result.
   
   AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy (main|MERGING)
   ```

   ``` bash
   #메모장에도 이렇게 표시됨
   hotfix 브랜치에서 수정
   <<<<<<< HEAD #이부분 삭제
   main 에서 수정 
   ======= #이부분 삭제
   hotfix 브랜치에서 또다시 수정합니다. 
   >>>>>>> hotfix #이부분 삭제
   
   #새롭게 생긴부분 삭제하고
   ```

   

   ```  bash
   #이렇게 과정 거치면 끝
   
   AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy (main|MERGING)
   $ git add .
   
   AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy (main|MERGING)
   $ git commit -m "merging"
   [main 6095cee] merging
   
   ```

   