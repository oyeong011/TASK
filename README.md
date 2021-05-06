# GIT

## 1) GIT과 GITHUB란?
* **GIT**

**GIT**은 우리가 개발 프로젝트를 진행할때 저장해주는 기능을 가진 시스템으로 이른바 버전관리를 해주는 것을 뜻합니다.

* **버전관리**

**버전관리**는 파일 변화를 시간에 따라 기록했다가 나중에 **특정 시점의 버전**을 다시 꺼내올 수 있는 것을 뜻합니다. 즉 하나의 **평행우주**를 만들어서 개발하다가 수정해야하면 그 시점으로 돌아갈수있다는 말입니다.

* **GITHUB**

여기서 그 깃을 이용해서 온라인에 저장할수있는 사이트가 있는데 그 중 하나가 **GITHUB**이라는 사이트입니다.

* **결론**

**git과 GitHub은 어떤 프로젝트를 수행하면서 산출되는 파일들의 버전 관리를 위해 사용합니다.**

## 2) GIT 명령어 사용법

 이 **파일의 목적**은 **GIT**에 대한 **명령어** 사용법을 알려주는 문서입니다. **가상의 프로젝트**를 수행하면서 쓰이게 되는 git 명령어에 대해서 알아볼것입니다.

 알아볼 명령어는 다음과 같습니다
* [config](#git-config)
* [init](#git-init)
* [add](#git-add)
* git status
* git branch
* git checkout
* git clone
* git commit
* git log
* git merge
* git pull
* git push
* git rebase
* git remote
* git reset
* git reset --hard
* git tag

### 프로젝트 설명

우리는 교수님에게 프로젝트 과제를 받았습니다. 그 프로젝트는 마크다운을 배운뒤 MARKDOWN을 사용한 MARKDOWN 튜토리얼을 만드는 것이었습니다. 과제일이 얼마 남지 않았으니까 빨리 시작해야겠습니다

* ### git init

* 빈파일 상태
빈파일 상태이므로 일단 마크다운을 설명하기위해서 md파일을 하나를 만들어야겠습니다.

1. 지금 상태는 윈도우에서 빈 폴더를 생성하고 vscode를 이용해서 빈폴더(이름:computer2)를 불러왔습니다. 그리고 프로젝트를 하기 위해 빈 md파일 하나만 만들어진 상태입니다.
2. 여기서 깃 저장소를 만들어서 깃을 사용해야합니다.
3. 그러기 위해서 ***git init***이라는 명령어를 이용해서 저장소를 만들것입니다.
4. 이 명령은 **.git** 이라는 하위 디렉토리를 만듭니다. 즉 프로젝트를 위해 만든 빈폴더(computer2)가 GIT의 관리하에 들어갔다는 말입니다. 그러면 computer2안에 숨겨진 깃파일이 생성되는데 이 안에 우리가 그때그때 코딩을 했던 순간에 있었던 파일들을 저장할 공간이 생긴것입니다. 윈도우에 생성된 파일 **.git** 디렉토리에는 저장소에 필요한 뼈대 파일(Skeleton)이 들어 있습니다. 하지만 이 명령만으로는 아직 프로젝트의 어떤 파일도 관리하지 않습니다.
![image](https://user-images.githubusercontent.com/53222742/117339147-5fe6d900-aeda-11eb-8508-411c971bb08a.png)

* ### git config
1. 빈파일에서 init을 입력하여 뼈대 파일이 생성된 상태입니다.
2. 깃을 제대로 사용하려면 초기 설정을 해줘야합니다. 그중에서 사용자 정보를 등록해줘야합니다. Git은 커밋할 때마다 이 정보를 사용하기 때문에 이 명령어는 필요합니다. 그리고 이것이 입력이 잘되었는지를 확인하고 싶습니다.
3. 이를 위해서 git config라는 명령어에서 
'''
git config --global user.name "이름"
git config --global user.email 이메일주소
git config --list
'''
5. 따라서 이 명령어는 사용자 정보를 등록하고 

![image](https://user-images.githubusercontent.com/53222742/117341480-1fd52580-aedd-11eb-8a29-8f40ff60905a.png)

* ### git status

1. 지금 상태는 git init을 이용해서 .git이라는 하위 디렉토리는 만든 상태입니다.
2. 지금 자신이 만든 파일의 상태를 확인하고 싶어졌습니다.
3. 이를 위해서 git status라는 명령어를 입력했습니다.
4. 따라서 git status는 깃 프로젝트의 상태를 확인할 때 사용하는 명령어입니다. 빨간색은 

![image](https://user-images.githubusercontent.com/53222742/117343167-fae1b200-aede-11eb-9be1-58b21d906096.png)

* ### git add

1. 지금 현 상태는 위의 사진 git status라는 
