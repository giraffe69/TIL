# TIL DAY1



<제목>

# 제목1#

## 제목2##

### 제목3###

#### 제목4####

##### 제목5#####

###### 제목6######

####### 제목7 (안됨)

<순서가 없는 목록>

-,+,*

- 순서가 없는 목록1
  - 서브 목록1 TAB누르면 서브목록
  - 서브 목록2
- 빠져나올려면 Shift + Tab / Enter

<순서가 있는 목록>

1. 순서가 있는 목록
   1. 서브 목록
      1. 서브 목록
      2. 서브목록
         - 서브목록
         - 서브목록

<강조>

- 기울임, 굵게,취소선
  - **기울임** : `*글자*` 혹은 `_글자_`  *글자*
  - **굵게** : `**글자**` 혹은 `__글자__`  **글자**
  - **취소** : `~~글자~~ ` ~~글자~~



<소스코드>

- 한 줄 코드 (인라인 코드 inline code)

  `print("Hellow world!")`  양쪽에 `

- 여러 줄 코드(블록 코드 block code) 양쪽에 ```

  ```python
  for i in range(10):
  	print(i)
  ```

  

<표(table)>

| 동물 이름 | 다리 개수 | 종     |
| --------- | --------- | ------ |
| 사자      | 4개       | 포유류 |
| 토끼      | 4개       | 포유류 |
| 앵무새    | 2개       | 조류   |

- 파이프( | )와 하이픈( - )을 이용해서 행과 열을 구분합니다.
- 테이블 양쪽 끝의 `파이프( | )`는 생략 가능합니다.
- 헤더 셀을 구분할 때는 3개 이상의 하이픈( - )이 필요합니다.

- 행 삭제 Ctrl + Shift + Backspace

- 행 늘리기 Crtl + Enter



<수평선>

- -,*,_ 세번 이상 반복하면 가능하다.

---

***

___





<실습1>



# Python



## 1.개요

![img](https://wikidocs.net/images/page/5/pahkey_KRRKrp.png)

파이썬(Python)은 1990년 암스테르담의 귀도 반 로섬(Guido Van Rossum)이 개발한 인터프리터 언어이다. 귀도는 파이썬이라는 이름을 자신이 좋아하는 코미디 쇼인 "몬티 파이썬의 날아다니는 서커스(Monty Python’s Flying Circus)"에서 따왔다고 한다.

> 인터프리터 언어란 한 줄씩 소스 코드를 해석해서 그때그때 실행해 결과를 바로 확인할 수 있는 언어이다.

## 2. 특징

1. **파이썬은 인간다운 언어이다. 아래 코드는 쉽게 해석된다.**

   `if 4 in [1,2,3,4]: print("4가 있습니다")`

​       만약 4가 1, 2, 3, 4 중에 있으면 "4가 있습니다"를 출력한다. 라고 말이다.

2. __파이썬은 간결하다.__

```python
# simple.py
languages = ['python', 'perl', 'c', 'java']

for lang in languages:
    if lang in ['python', 'perl']:
        print("%6s need interpreter" % lang)
	elif lang in ['c', 'java']:
		print("%6s need compiler" % lang)
	else:
		print("should not reach here"
```

3. 공식문서가 자세히 제공된다.

​	  [파이썬 공식문서 링크](https://docs.python.org/3/)



# Git 특강 #1

## 1.CLI

__경로__

- 파일이나 폴더의 고유한 위치를 나타내는 문자열(주소)

- 운영체제에 따라서 다르게 표현된다.

  windows - C:\\\Users\\\Document

  macOS - /Users/Document

## 루트 디렉토리

- 모든 파일/폴더를 담고 있는 폴더
- windows의 경우 보통 C 드라이브를 의미함

## 상대 경로

* 현재 워킹 디렉토리를 기준으로 계산된 경로
* 현재 워킹 디렉토리가 `C\\\Users\\\User\\\바탕화면` 라면 `C:\\\\Users\\\User\\\바탕 화면\\\code` 의 상대 경로는 `code` 가 된다.
* 간결해서 좋지만 만약 현재 워킹 디렉토리가 변한다면 상대 경로는 변경된다.(다시 계산해야함)



## [1] Git 초기 설정

> 최초 한 번만 설정합니다. 매번 Git을 사용할 때마다 설정할 필요가 없습니다.

1. 누가 커밋 기록을 남겼는지 확인할 수 있도록 이름과 이메일을 설정합니다.

   작성자를 수정하고 싶을 때에는 이름, 메일 주소만 다르게 하여 동일하게 입력합니다.

   ```bash
   $ git config --global user.name "이름"
   $ git config --global user.email "메일 주소"
   ```

2. 작성자가 올바르게 설정되었는지 확인 가능합니다.

   ```bash
   $ git config --global -l
   
   또는
   
   $ git config --global --list
   ```

## [2] Git 기본 명령어

### (0) 로컬 저장소

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7142d992-3d01-481c-9d4e-e818c6e185d8/Untitled.png)

- `Working Directory (= Working Tree)` : 사용자의 일반적인 작업이 일어나는 곳
- `Staging Area (= Index)` : 커밋을 위한 파일 및 폴더가 추가되는 곳
- `Repository` : staging area에 있던 파일 및 폴더의 변경사항(커밋)을 저장하는 곳
- Git은 **Working Directory → Staging Area → Repository** 의 과정으로 버전 관리를 수행합니다.

### (1) git init

```bash
$ git init
Initialized empty Git repository in C:/Users/kyle/git-practice/.git/

kyle@KYLE MINGW64 ~/git-practice (master)
```

- 현재 작업 중인 디렉토리를 Git으로 관리한다는 명령어
- `.git` 이라는 숨김 폴더를 생성하고, 터미널에는 `(master)`라고 표기됩니다.
- Mac OS의 경우 `(master)`가 표기되지 않는데, Terminal 업그레이드를 통해 표기할 수 있습니다.

<aside> ❗ **주의 사항**

1. 이미 Git 저장소인 폴더 내에 또 다른 Git 저장소를 만들지 않습니다. (중첩 금지) 즉, 터미널에 이미 (master)가 있다면, git init을 절대 입력하면 안됩니다.
2. 절대로 홈 디렉토리에서 git init을 하지 않습니다. 터미널의 경로가 `~` 인지 확인합니다.

</aside>

### (2) git status

```bash
$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

- Working Directory와 Staging Area에 있는 파일의 현재 상태를 알려주는 명령어

- 어떤 작업을 시행하기 전에 수시로 status를 확인하면 좋습니다.

- 상태

  1. `Untracked` : Git이 관리하지 않는 파일 (한번도 Staging Area에 올라간 적 없는 파일)

  2. ```
     Tracked
     ```

      : Git이 관리하는 파일

     1. `Unmodified` : 최신 상태
     2. `Modified` : 수정되었지만 아직 Staging Area에는 반영하지 않은 상태
     3. `Staged` : Staging Area에 올라간 상태

  ![파일의 라이프사이클](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/67719520-a1d8-4cbb-81dd-49dea429a7f4/Untitled.png)

  파일의 라이프사이클

### (3) git **add**

```bash
# 특정 파일
$ git add a.txt

# 특정 폴더
$ git add my_folder/

# 현재 디렉토리에 속한 파일/폴더 전부
$ git add .
```

- Working Directory에 있는 파일을 Staging Area로 올리는 명령어

- Git이 해당 파일을 추적(관리)할 수 있도록 만듭니다.

- `Untracked, Modified → Staged` 로 상태를 변경합니다.

- 예시

  ```bash
  $ touch a.txt b.txt
  
  $ git status
  On branch master
  
  No commits yet
  
  Untracked files: # 트래킹 되고 있지 않는 파일 목록
    (use "git add <file>..." to include in what will be committed)
          a.txt
          b.txt
  
  nothing added to commit but untracked files present (use "git add" to track)
  ```

  ```bash
  # a.txt만 Staging Area에 올립니다.
  
  $ git add a.txt
  ```

  ```bash
  $ git status
  
  On branch master
  
  No commits yet
  
  Changes to be committed: # 커밋 예정인 변경사항(Staging Area)
    (use "git rm --cached <file>..." to unstage)
          new file:   a.txt
  
  Untracked files: # 트래킹 되고 있지 않은 파일
    (use "git add <file>..." to include in what will be committed)
          b.txt
  ```

### (4) git **commit**

```bash
$ git commit -m "first commit"
[master (root-commit) c02659f] first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 a.txt
```

- Staging Area에 올라온 파일의 변경 사항을 하나의 버전(커밋)으로 저장하는 명령어
- `커밋 메세지`는 현재 변경 사항들을 잘 나타낼 수 있도록 `의미` 있게 작성하는 것을 권장합니다.
- 각각의 커밋은 `SHA-1` 알고리즘에 의해 반환 된 고유의 해시 값을 ID로 가집니다.
- `(root-commit)` 은 해당 커밋이 최초의 커밋 일 때만 표시됩니다. 이후 커밋부터는 사라집니다.

### (5) **git log**

```bash
$ git log
commit 1870222981b4731d14ef91d401c68c0bbb2f6e7d (HEAD -> master)
Author: kyle <kyle123@hphk.kr>
Date:   Thu Dec 9 15:26:46 2021 +0900

    first commit
```

- 커밋의 내역(`ID, 작성자, 시간, 메세지 등`)을 조회할 수 있는 명령어
- 옵션
  - `--oneline` : 한 줄로 축약해서 보여줍니다.
  - `--graph` : 브랜치와 머지 내역을 그래프로 보여줍니다.
  - `--all` : 현재 브랜치를 포함한 모든 브랜치의 내역을 보여줍니다.
  - `--reverse` : 커밋 내역의 순서를 반대로 보여줍니다. (최신이 가장 아래)
  - `-p` : 파일의 변경 내용도 같이 보여줍니다.
  - `-2` : 원하는 갯수 만큼의 내역을 보여줍니다. (2 말고 임의의 숫자 사용 가능)

<aside> 💡 **옵션과 인자**

명령어를 사용하면서 `-` 혹은 `--`를 통해 옵션을 사용하는 것을 배웠습니다. 옵션과 더불어서 인자라는 개념도 존재하는데요. 옵션과 인자 무엇이 다를까요?

—-

`옵션`은 명령어의 `동작 방식`을 지정하는 것입니다. 따라서 **생략 가능**합니다. 단순히 기존 기능보다 부가 적인 기능을 원할 때 사용합니다. 예를 들면 `git log --oneline`은 커밋 내역을 한 줄로 보고 싶을 때 사용합니다. `oneline` 옵션은 말 그대로 부가 적인 기능이므로, 생략해도 `git log`는 정상 동작 합니다.

—-

`인자`는 명령어의 `동작 대상`을 지정하는 것입니다. 따라서 **생략이 불가능** 합니다. 예를 들면 `git add` 라고만 작성하면 어떤 파일을 Staging Area에 올릴지 모르게 됩니다. 반드시 `git add a.txt` 와 같이 git add 명령어가 동작할 대상을 지정해야 하는데 이때 `a.txt`와 같은 대상을 인자라고 합니다.

</aside>

### (6) 한눈에 보는 Git 명령어

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c86c667a-616f-45b6-892e-15da6a3c494e/Untitled.png)





1. Git 환경설정 (최초 1번만 하면 됨)
git config --global user.name edukyle
git config --global user.email edukyle.hphk@gmail.com

git config --global --list

2. git 로컬 저장소 만들기
git init

3. git 파일 상태 보기
git status

4.  Working Directory -> Staging Area
git add a.txt

5.  Staging Area -> Commits
git commit -m "commit message"

6. git 커밋 목록 보기
git log
git log --oneline
git log -p