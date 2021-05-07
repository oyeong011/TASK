https://github.com/oyeong011/TASK/blob/main/README.md
# GIT

## 1) GIT과 GITHUB란?
* **GIT**

**GIT**은 소프트웨어 개발에서 소스 코드를 효과적으로 관리할 수 있도록 하는 무료, 공개 소프트웨어이다. 이것의 기능은 프로젝트 폴더 내에서 작업을 기록하고, 버전 관리를 통해 체계적인 개발이 가능하도록 한다.

* **버전관리**

**버전관리**는 파일 변화를 시간에 따라 기록했다가 나중에 **특정 시점의 버전**을 다시 꺼내올 수 있는 것을 뜻합니다. 즉 하나의 **평행우주**를 만들어서 개발하다가 수정해야하면 그 시점으로 돌아갈수있다는 말입니다.

* **GITHUB**

여기서 그 깃을 이용해서 온라인에 저장할수있는 사이트가 있는데 그 중 하나가 **GITHUB**이라는 사이트입니다.

* **결론**

**git과 GitHub은 어떤 프로젝트를 수행하면서 산출되는 파일들의 버전 관리를 위해 사용합니다.**

## 2) GIT 명령어 사용법

 이 **파일의 목적**은 **GIT**에 대한 **명령어** 사용법을 알려주는 문서입니다. **가상의 프로젝트**를 수행하면서 쓰이게 되는 git 명령어에 대해서 알아볼것입니다.

 알아볼 명령어는 다음과 같습니다
* [init](#git-init)
* [config](#git-config)
* [add](#git-add)
* [status](#git-status)
* [commit](#git-commit)
* [log](#git-log)
* [reset](#git-reset)
* [branch](#git-branch)
* [checkout](#git-checkout)
* [merge](#git-merge)
* [rebase](#git-rebase)
* [remote](#git-remote)
* [push](#git-push)
* git pull
* git clone
* git tag

### 프로젝트 설명

우리는 교수님에게 프로젝트 과제를 받았습니다. 그 프로젝트는 마크다운을 배운뒤 MARKDOWN을 사용한 MARKDOWN 튜토리얼을 만드는 것이었습니다. 과제일이 얼마 남지 않았으니까 빨리 시작해야겠습니다

* ### git init

* 빈파일 상태
빈파일 상태이므로 일단 마크다운을 설명하기위해서 md파일을 하나를 만들어야겠습니다.

1. 지금 상태는 윈도우에서 빈 폴더를 생성하고 vscode를 이용해서 빈폴더(이름:computer2)를 불러왔습니다. 그리고 프로젝트를 하기 위해 빈 md파일 하나만 만들어진 상태입니다.
2. 여기서 깃 저장소를 만들어서 깃을 사용해야합니다.
3. 그러기 위해서 ***git init***이라는 명령어를 이용해서 저장소를 만들것입니다.
```
$git init
```
4. 이 명령은 **.git** 이라는 하위 디렉토리를 만듭니다. 즉 프로젝트를 위해 만든 빈폴더(computer2)가 GIT의 관리하에 들어갔다는 말입니다. 그러면 computer2안에 숨겨진 깃파일이 생성되는데 이 안에 우리가 그때그때 코딩을 했던 순간에 있었던 파일들을 저장할 공간이 생긴것입니다. 윈도우에 생성된 파일 **.git** 디렉토리에는 저장소에 필요한 뼈대 파일(Skeleton)이 들어 있습니다. 하지만 이 명령만으로는 아직 프로젝트의 어떤 파일도 관리하지 않습니다.
![image](https://user-images.githubusercontent.com/53222742/117339147-5fe6d900-aeda-11eb-8508-411c971bb08a.png)

![image](https://user-images.githubusercontent.com/53222742/117341480-1fd52580-aedd-11eb-8a29-8f40ff60905a.png)

* ### git config
1. 빈파일에서 init을 입력하여 뼈대 파일이 생성된 상태입니다.
2. 깃을 제대로 사용하려면 초기 설정을 해줘야한다.그중에서 사용자 정보를 등록해줘하고 이것이 입력이 잘되었는지를 확인하고자 한다.
3. 이를 위해서 git config라는 명령어에서 다음과 같은 명령어를 입력한다.
```
$git config --global user.name "이름" : 이름등록
$git config --global user.email 이메일주소 : 이메일 주소 등록
$git config --list : 설정한 모든 것을 리스트로 확인
```
4. 따라서 이 명령어는 사용자 정보를 등록하고 등록이 잘되었는지 확인하는 것으로 **설정 내용을 확인하고 변경할 수 있다.**
5. 이 명령어의 자주쓰이는 옵션으로는 **--global**이 있다. 이것은 특정 사용자(즉 현재 사용자)에게만 적용되는 설정이다. **git config --global** 옵션으로 이 파일을 읽고 쓸 수 있다. 특정 사용자의 모든 저장소 설정에 적용된다. **하지만 초기 설정을 하는 명령어라 거의 한번만 필수적으로 입력하고 다시 쓰지 않는 명령어라고 생각한다.** 

![image](https://user-images.githubusercontent.com/53222742/117351585-ddb1e100-aee8-11eb-9b3d-a6ada350b1c5.png)

* ### git status

1. 지금 상태는 git init을 이용해서 .git이라는 하위 디렉토리는 만든 상태입니다.
2. 지금 자신이 만든 파일의 상태를 확인하고 싶어졌습니다.
3. 이를 위해서 git status라는 명령어를 입력했습니다.
4. 따라서 git status는 깃 프로젝트의 상태를 확인할 때 사용하는 명령어입니다. 빨간색은 Untracked(관리대상이 아님)을 뜻한다.

![image](https://user-images.githubusercontent.com/53222742/117343167-fae1b200-aede-11eb-9be1-58b21d906096.png)

* ### git add

1. 지금 현 상태는 위의 사진 git status라는 명령어를 입력해서 지금 프로젝트의 상태를 확인했고 sample.md가 Untracted 상태 즉 깃이 이 sample.md파일을 보고있지 않은 상태를 뜻한다.또 빨간색으로 표시된 sample.md는 파일이 만들어졌다는 사실을 지칭한다.
2. 지금까지 작업했던 파일들의 변경점을 저장하고 싶습니다.
3. 그래서 다음과 같은 명령어를 입력했습니다.
```
git add -A
```
4. 따라서 git add 명령어는 다음 변경을 기록할 때까지 변경분을 모아놓기 위해서 사용한다. 비유하자면 타임캡슐을 만드는 과정이다. 필자의 생각으로 자주 쓰이는 옵션은 다음과 같다.
```
$ git add <파일/디렉토리 경로> : 작업 디렉토리의 변경 내용의 일부만 넘기고 싶을 때는 수정한 파일이나 디렉토리의 경로를 인자로 넘긴다.
$ git add . : 현재 디렉토리의 모든 변경 내용을 스테이징 영역으로 넘기고 싶을 때는, .을 인자로 넘긴다.
$ git add -A : 작업 디렉토리 내의 모든 변경 내용을 몽땅 넘기고 싶을 때 사용
$ git add -p : 각 변경 사항을 터미널에서 직접 눈으로 하나씩 확인하면서 넘기거나 또는 제외할 수가 있다.
```
사진을 보면 변경된 점들이 타임캡슐에 들어간 것을 확인할 수 있다.

![image](https://user-images.githubusercontent.com/53222742/117355502-9e39c380-aeed-11eb-8b97-9e9e5e4cd369.png)

* ### git commit

1. git add를 통해서 스테이싱 영역 즉 타임캡슐에 파일 변경점을 저장해놓은 상태다.
2. 이 스테이싱 영역을 저장하고자한다. 즉 타임캡슐을 땅에 묻어서 완전한 형태의 저장을 하고자 한다.
3. 다음과 같은 명령어를 입력한다.
```
$git commit
```
4. 따라서 이 명령어는 add로 스테이싱영역에 저장된 기록들을 저장하는 역할을 한다. 비유하자면 타임캡슐 상자를 만들고 이를 깃저장소라는 땅에 묻어서 저장하는 것을 말한다.
5. 필자가 생각하기에 commit에서 자주 쓰이는 옵션은 다음과 같다.
```
&git commit -m "설명" : 커밋으로 저장할때 커밋에 어떤점이 바뀌었는지 쓸수있는 기능
```
![image](https://user-images.githubusercontent.com/53222742/117358050-a810f600-aef0-11eb-8822-05034292cc55.png)

* ### 중간정리

1. 프로젝트를 3분의 1정도 수행한 상태
2. 프로젝트에서 변경된 사항들을 저장하고자한다.
3. 다음과 같은 명령어를 입력한다.
```
$git status : 프로젝트에서 변경된 사항중에 스테이싱영역(타임캡슐)에 들어가있는지 없는 지 상태를 확인
&git add -A : sample.md의 변경점이 스테이싱영역에 없는 것을 보고 스테이싱영역에 집어넣기
$git commit -m "Second record" : 스테이싱영역을 커밋을 통해서 변경점을 저장소에 넣기, 이름은 Second record라고 표시 
```
이과정을 2번정도 반복해서 프로젝트의 3분의 2 분량을 해낸 상태다. * 커밋을 할때마다 Second, Third, Fourth record라고 작성해서 커밋을 분류함

![image](https://user-images.githubusercontent.com/53222742/117363511-a39c0b80-aef7-11eb-9fc3-29dbdd52166a.png)

* ### git log

1. 커밋을 3번정도 수행하고 프로젝트가 3분의 2정도 해결된 상태
2. 자기가 몇번 커밋을 했는지 커밋 히스토리를 알고자한다. 즉 땅에 묻은 캡슐이 몇개고 어디에 있는지 확인하고자한다.
3. 다음과 같은 명령어를 작성한다.
```
$git log
```
4. 이 명령어는 저장소의 히스토리를 보고자 할때 히스토리를 조회하는 명령어이다.

![image](https://user-images.githubusercontent.com/53222742/117365092-c16a7000-aef9-11eb-986f-a0e7295c5b92.png)

5. 필자가 생각하기에 log에서 자주쓰이는 옵션은 다음과 같다.
```
$git log -2 : 최근 두 개의 결과만 보여주는 옵션
$git log -p :  각 커밋의 diff(다른점) 결과를 보여준다
```

* ### git reset

1. 프로젝트를 3번정도 커밋했으나 문서의 가독성이 이상해보임
2. 문서를 2번째 커밋으로 되돌리고싶음
3. 다음과 같은 명령어를 입력한다.
```
$git log : 로그를 통해 이동할 커밋의 주소를 확인
$git reset 1e3397 --hard : 알아낸 주소를 바탕으로 reset을 함 : git reset [되돌아가고자하는커밋주소]  [옵션]
```
4. 이 명령어는 코드를 잘못 작성했을때 되돌리고 싶을 때 쓰는 명령어이다.
5. 필자가 생각하는 자주쓰이는 명령어는 다음과 같다.
```
$git reset 주소 --hard : 돌아가려는 이력이후의 모든 내용을 지워 버린다. 영화로 비유를 들면 표를 예매하고, 팝콘과 사이다를 구매했던 모든 것들이 지워지고 모든것이 초기화 되는것이다.
```
![image](https://user-images.githubusercontent.com/53222742/117371134-596c5780-af02-11eb-9aef-dd21b367c53e.png)

* ### git branch

1. 2번째 커밋으로 돌아가서 다시 수정해야하는 상태
2. 수정을 해야하는데 수정전에 새로운 아이디어가 생각이 나서 복제파일을 만들어서 실험적인 내용을 다루는 필드가 필요함
3. 다음과 같은 명령어를 입력
```
$git branch my-idea : git branch 브랜치명
```
4. 이 명령어는 여러 개발자들이 동시에 다양한 작업을 할 수 있게 브런치(복사된 필드)를 만들어 주는 기능이 있다.
5. 필자가 생각하기에 이 명령어에서 자주 쓰이는 옵션은 다음과 같다
```
$git branch -D (브랜치명) : 생성한 브랜치를 지워주는 역할을 한다.
```
* ### git checkout

1. 브랜치를 생성한 상태고 지금은 마스터 브랜치에 위치해있는 상태
2. 새로 만든 my-idea 브랜치에 옮겨서 작업하고자함
3. 다음과 같은 명령어를 입력한다.
```
$git checkout my-idea : 해당 브렌치로 이동하는 명령어
```

4. 이 명령어는 앞에서 새로 만든 'my-idea'라는 이름의 브랜치를 사용하여 어떤 작업을 수행하려면, 이 브랜치를 사용 하겠다고 명시적으로 지정해야함. 즉 체크아웃(checkout)이란, 사용할 브랜치를 지정하는 것을 의미합니다.

* branch&checkout
![image](https://user-images.githubusercontent.com/53222742/117373676-a9e5b400-af06-11eb-858b-e043cd29ed91.png)

5. 필자가 생각하는 이 명령어에서 자주쓰이는 옵션은 다음과 같다.

```
$git checkout -b 브랜치명 : 새로운 브랜치를 만들고 그 브랜치로 이동할 수 있다.
```

* ### git merge

1. 새로운 브런치 my-idea에서 새로운 아이디어를 이용해 커밋하여 추가함
2. 기존에 있던 마스터 브런치와 병합하고자함
3. 다음과 같은 명령어를 입력한다.

```
$git checkout master : 처음에 있던 최초 브랜치로 이동 첫번째 브랜치의 이름은 자동으로 master라고 설정된다.
&git merge my-idea : git merge 병합하고자하는 브랜치 : 두 개의 부모(parent)를 가리키는 특별한 커밋을 만들어낸다.
```
merge를 한번하면 이런상태로 남는다. 즉 master브랜치는 두 부모가 있는 커밋을 가르키지만 my-idea는 브랜치가 합쳐지지 않은 것이다. 따라서 my-idea도 병합하려면 위의 과정에서 master와 my-idea를 바꿔주면된다.

![image](https://user-images.githubusercontent.com/53222742/117405795-26988280-af47-11eb-8941-433db477d17a.png)


```
$git checkout my-idea : 처음에 있던 최초 브랜치로 이동 첫번째 브랜치의 이름은 자동으로 master라고 설정된다.
&git merge master : git merge 병합하고자하는 브랜치 : 두 개의 부모(parent)를 가리키는 특별한 커밋을 만들어낸다.
```

그러면 이런 상태가 된다.

![image](https://user-images.githubusercontent.com/53222742/117406118-91e25480-af47-11eb-8cf3-a487ff59a363.png)

![image](https://user-images.githubusercontent.com/53222742/117406299-d79f1d00-af47-11eb-9bf4-0e6f0354cd29.png)

4. 따라서 merge라는 명령어는 서로 다른 두 브랜치를 합칠 때 사용되는 명령어 즉 한 부모의 모든 작업내역과 나머지 부모의 모든 작업, 그리고 그 두 부모의 모든 부모들의 작업내역을 포함한다.

* ### git rebase

1. 프로젝트에 대한 새로운 아이디어가 떠올라서 새로운 브랜치인 my-another-idea를 생성해서 새로운 내용과 사진파일을 추가한 상태
2. 이를 또한 병합하고자합니다. 그러나 커밋의 수와 브랜치의 수가 많아져서 이를 깔끔하게 병합하고자한다.
3. 다음과 같은 명령어를 입력한다.
```
$git checkout my-another-idea : 브랜치 위치를 my-another-idea로 이동
$git rebase master : 본인의 브랜치 커밋들을 복사해서 master 밑에 위치와 함께 붙여넣기
$git checkout master : 브랜치 위치를 master으로 이동 
$git rebase my-another-idea : 브랜치의 위치를 my-another-idea로 이동
```
결과는 그림과 같다
![image](https://user-images.githubusercontent.com/53222742/117415649-8137db80-af53-11eb-87ed-c990b2852d02.png)

4. 따라서 이 명령어는 브랜치를 병합할때 사용하고 좀 더 깨끗한 히스토리를 만들때 사용한다.

![image](https://user-images.githubusercontent.com/53222742/117417445-5058a600-af55-11eb-86e4-146817350381.png)

* ### git remote

1. 프로젝트가 어느 정도 완성이 되어감
2. 이를 다른 사람들과 공유하고 보완할점을 조언받고자 깃허브에 올리고자 저장소를 마련해야함
3-1. 깃허브에 가입하고 레퍼지토리를 생성함
3-2. 다음과 같은 명령어를 이용해 저장소를 연결
```
$git remote add origin https://github.com/oyeong011/TASK.git : git remote add origin (깃허브주소)
```
4. 위에서 알아보았던 git init과 같은 역할을 깃허브 버전으로 구현한 것이다. 즉 깃허브에서 생성한 레포지토리를 vscode에서 생성한 파일과 연결시켜주는 것이다.

![image](https://user-images.githubusercontent.com/53222742/117435626-05488e00-af69-11eb-900a-de1b26bd1294.png)

5. 필자가 생각하는 자주 쓰이는 옵션은 다음과 같다.
```
$git remote : 현재 연결된 레포지토리 이름을 확인할수있다
$git remote add (리모트이름) (경로) : 새 리모트를 추가합니다. (경로)영역에는 URL이나 파일경로를 넣을수 있음
$git remote -v : 등록된 저장소 이름과 URL을 표시함
$git remote show (리모트이름) : 모든 리모트 경로의 branch와 정보를 표시
$git remote rm (리모트이름) : 리모트 경로를 제거
```

* ### git push

1. 프로젝트를 깃허브 레포지토리에 연결한 상태
2. 필자가 만든 프로젝트를 레포지토리에 올리고자함
3. 다음과 같은 코드를 사용한다.
```
$git push otigin master
```

![image](https://user-images.githubusercontent.com/53222742/117436677-34abca80-af6a-11eb-9dd1-9f183f3f93ee.png)


* ### git clone

* git pull
