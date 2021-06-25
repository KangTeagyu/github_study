# CLI

## ls(list)

- ls 명령어는 현재 작업중인 위치의 존재하는 파일, 폴더 목록을 보여줌.

```bash
AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy
$ ls
text.txt

```



## cd(change directory)

- 현재 작업중인 디렉토리(a.k.a 폴더)를 변경하겠다.

  ``` bash
  AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy
  $ cd
  $ cd.. #내 상위 폴더로 이동
  ```

  

## mkdir(make directory)

- 디렉토리/폴더 생성한다.

  ``` bash
  AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy
  $ mkdir {directory name}
  ```

  

## touch 

- 파일을 생성한다.

  ``` bash
  $touch {file name}.확장자
  ```

  

## ctrl+l

- 깔끔하게 구문 삭제



## Git 초기설정

- 커밋 작성자 설정

- ``` bash
  AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy
  $ git config --global user.email ktg0527@naver.com
  
  AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy
  $ git config --global user.name KangTeagyu
  #명령을 실행시키고자 하는 주체
  ```

  

- 지정된 설정 확인

  ``` bash
  #git아 현재 전역에 설정된 설정 목록 보여줘
  AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy
  $ AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy
  filter.lfs.clean=git-lfs clean -- %f
  filter.lfs.smudge=git-lfs smudge -- %f
  filter.lfs.process=git-lfs filter-process
  filter.lfs.required=true
  user.name=KangTeagyu
  user.email=ktg0527@naver.com
  core.autocrlf=false
  #여태 했던 설정 보여줌
  ```

  

## Git Basic

## 로컬저장소 설정

``` bash
$ git init

#폴더에 .git 숨김폴더 생김
#bash에는 (master)라는 표시가 생김
AzureAD+강태규@DESKTOP-LBJDA7T MINGW64 ~/Desktop/gitstudy (master)


```

- 주의사항 .git 폴더 직접적으로 수정할 일 없다.
- 이미 git으로 관리하고 있는 (bash창에 master가 표시되어있는 폴더내에서는 절대 git init 하지 말것)

## status

``` bash
#git아 너가 관리중인 폴더의 상태 보여줘
$ git status
```



## add

``` bash
$ git add 파일명
$ git add . #현재 디렉토리
$ git add a.txt # 특정파일
$ git add directory_name/ # 특정폴더가 가진 모든 파일
```

- working directory 상태의 staging area 상태로 변경



## commit

```bash
#git아, 커밋할건데 -메세지는 "이걸로 해줘"
$ git commit -m "commitmessage"
```

## git log

``` bash
$ git log # git log --oneline 은 한줄로 보여준다.
Author: KangTeagyu <ktg0527@naver.com>
Date:   Thu Jun 24 15:54:46 2021 +0900

    2021-06-24, UI 대개편

commit 0e37325a1d4291b69b5d5b16d6c868f7d406a967
Author: unknown <eric71804122@gmail.com>
Date:   Sun Jun 20 23:46:01 2021 +0900

    출시 준비 및 요일 레이아웃 추가

commit cc735c7240d1163be256ce019527e2f85441a9e8
Author: KangTeaGyu <ktg0527@naver.com>
Date:   Sun Jun 20 19:16:05 2021 +0900

    2021-06-20, 카드뷰 추가

commit f921ec9642583f379542c5ff17ea9516cbf759cc
Author: unknown <eric71804122@gmail.com>
Date:   Sun Jun 20 13:45:34 2021 +0900

    아,점,저 수정

commit be40b40f2946e0e377eef3b740df2a8cbdb9068c
Author: unknown <eric71804122@gmail.com>
Date:   Sat Jun 19 20:27:33 2021 +0900

    fix

commit ebdc3cdad6f3fa1632a4cedace938c528db394e1
Author: KangTeaGyu <ktg0527@naver.com>
Date:   Sat Jun 19 18:55:44 2021 +0900

    2021-06-19 수정

commit 75beeed02f734163d47de312c27ff020f1651716
Author: unknown <eric71804122@gmail.com>
Date:   Sun Jun 13 13:03:05 2021 +0900

    remote test

commit ffa57d3d92845fa34ee63c7602e42ddf4696b083
Author: KangTeagyu <ktg0527@naver.com>

```

- commit 로그 목록



## 기본설정

1. 로컬 git 저장소 준비
2. github repository 생성
3. repository default branch 변경

## 명령어

## 원격저장소 주소 추가

``` bash
#원격 저장소 주소 origin이라는 이름으로 추가할건데 주소는 이거야!
$ git remote add origin https:// ~

```



## 원격 저장소 목록 보기

``` bash
$ git remote -v
```



## 원격 저장소에 업로드(push)

``` bash
$ git push -u origin main(master)

#commit 내역 없으면 업로드 불가능
#git아 origin이라는 이름으로 저장해둔 원격 저장소에 내용들 
```



## 원격 저장소 내용 전체 복제

``` bash
git clone {원격저장소 url}

```



## pull

- 원격 저장소의 변경사항을 받아옴(업데이트)

  ``` bash
  $ git pull origin master
  ```

  
