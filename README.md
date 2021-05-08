# GitPractice
## 1. config
- 처음 git을 설치하면 아무 설정도 되어있지 않을 것이다.
- 그러나 git은 커밋 할 때마다 사용자 이름과 이메일 주소를 사용한다. 따라서 git의 최초설정을 해주는 명령어가 필요하다.
- 이를 위해 git 명령어 ‘git config --global' 을 사용하였다.
- 따라서 config 명령어는 git의 최초설정을 위한 명령어이며, 특히 --global 옵션을 사용하여 사용자의 이름과 이메일 주소등을 설정하기 위해 사용하는 것이라 할 수 있다. 그리고 config 명령어의 자주 사용할 것 같은 또 다른 옵션으로는 ‘git config --list' 가 있다. 이 옵션은 설정된 목록을 확인할 수 있도록 해준다.

![1](https://user-images.githubusercontent.com/80791532/117521006-6d898500-afe6-11eb-936e-e1d572af2640.PNG)

![2](https://user-images.githubusercontent.com/80791532/117521022-809c5500-afe6-11eb-81fb-64f54dc3af80.PNG)

## 2. init
- git을 사용하기 위한 최초 설정은 하였지만 아직 아무것도 할 수 없는 상태이다.
- 따라서 git이 버전관리를 해주는 상태로 만들어주는 명령어가 필요하다.
- 이를 위해 git 명령어 'init'을 사용하였다.
- 따라서, init 명령어는 현재 자신이 위치하고 있는 디렉터리를 기준으로 git 저장소를 생성하여 자신이 위치하고 있는 폴더가 git의 관리 하에 들어가게 하기 위해 사용되는 것으로 정리할 수 있다. 그리고 init 명령어의 자주 사용할 것 같은 또 다른 옵션으로는 ‘git init --bare' 가 있다. 이 옵션은 로컬 저장소가 아닌 원격저장소를 생성해준다.

![image](https://user-images.githubusercontent.com/80791532/117521097-e7ba0980-afe6-11eb-9fcd-d192f0c8f393.png)

## 3. status
- 현재 문서가 위치하고 있는 디렉터리는 git의 관리 하에 있다.
- 이 때 디렉터리 안의 파일이 수정되었는지 파일의 상태를 확인하고 싶다.
- 이를 위해 git 명령어 ‘status’를 사용하였다.
- 따라서, 이 'status' 명령어는 파일을 수정하였는지(git이 파일을 추적하는 상태인지) 확인하기 위해 사용되는 명령어라 할 수 있다. 만약 파일의 상태가 untracked 라면 아직 파일을 하나도 수정하지 않았다는 의미이다. 따라서 untracked 상태는 파일들이 만들어지긴 했지만 만들어졌다는 사실만 알 뿐이다. git은 절대  untracked 상태 파일을 커밋하지 않는다. 그리고 status 명령어의 자주 사용할 것 같은 또 다른 옵션으로는 ‘git status -s' 가 있다. 이 옵션은 git status 명령으로 확인할 수 있는 내용을 좀 더 요약해서 보여준다.

![4](https://user-images.githubusercontent.com/80791532/117521138-2d76d200-afe7-11eb-80f2-3051b7237c32.PNG)

## 4. add
- 현재 문서는 untracked 상태(git이 파일을 추적하지 않는 상태)이다. 
- 이 상태에서 git이 파일을 추적하는 상태로 만들고 싶다.
- 이를 위해 git 명령어 ‘add’중에서도 ‘git add .' (현재 디렉토리의 모든 변경 내용을 staging area로 넘김) 명령어를 사용했다.
- 따라서 'add'명령어는 해당 파일을 staging area(커밋할 준비가 된 변경 내용이 Git 저장소에 기록되기 전에 대기하는 장소) 에 저장하여 Tracked 상태, 즉, git이 파일을 추적하고 관리하는 상태로 만들기 위해 사용하는 것으로 정리할 수 있다. 그리고 add 명령어의 자주 사용할 것 같은 또 다른 옵션으로는 ‘git add -A’와 ‘git add -p’ 가 있다. ‘git add -A’는 작업 디렉토리 내의 모든 내용을 몽땅 staging area로 넘기고 ‘git add -p’ 는 각 변경사항을 터미널에서 직접 눈으로 하나씩 확인하면서 staging area로 넘기거나 제외할 수 있다. 

![5](https://user-images.githubusercontent.com/80791532/117521218-91999600-afe7-11eb-86bc-43c067af196b.PNG)

## 5. commit
- 현재 문서는 tracked 상태이며 staging area에 저장되어 있다.
- 이 상태에서 파일을 git저장소에 저장하고 싶다.
- 이를 위해 git 명령어 ‘commit’ 중에서도 ‘git commit -m <커밋 메시지>’ 를 사용했다.(이때 커밋 메시지는 해당 작업이 무엇을 했는지를 잘 표현해야 한다)
- 따라서, ‘commit'명령어는 add 될 때의 파일의 상태를 git저장소에 저장하는 명령어라고 할 수 있다. 이때 git add 명령으로 추가하지 않은 파일은 커밋하지 않으며 Unstaged 상태의 파일은 커밋되지 않는다. 그리고 status 명령어의 자주 사용할 것 같은 또 다른 옵션으로는 ‘git commit -a’가 있다. 별도의 add명령어를 사용하지 않고도 수정된 파일에 대해 add명령과  commit명령을 한 번에 수행한다.

![6](https://user-images.githubusercontent.com/80791532/117521328-2a301600-afe8-11eb-9257-4080b2774249.PNG)

## 6. log
- 현재 문서는 최초 커밋이 된 뒤에 필요없는 문장의 삭제가 이루어진 후 다시 한 번 커밋이 된 상태이다.
- 이 상태에서 git 저장소의 히스토리를 보고 싶다.
- 이를 위해 ‘log’ 명령어를 사용하였다.
- 따라서, ‘log’명령어는 git의 히스토리를 조회하여 저장소의 커밋 히스토리를 시간순으로 보여주는 명령어 라고 할 수 있다. 이때 가장 최근의 커밋이 가장 먼저 나온다. 그리고 log 명령어의 자주 사용할 것 같은 또 다른 옵션으로는 'git log -p'와 ‘git log --patch’ 가 있다. 'git log -p'와 ‘git log --patch’는 각 commit의 (변경사항)diff결과를 줄 단위로 보여준다. 따라서 동료가 무엇을 커밋했는지 빨리 조회하는데 유용하다.

![8](https://user-images.githubusercontent.com/80791532/117522177-d07e1a80-afec-11eb-8c35-0dbdab00d8b7.PNG)

## 7. reset --hard
- 현재 문서는 문맥이 맞지 않는 문장을 수정한 뒤 다시 한 번 커밋이 이루어진 상태이다.
- 그러나 다시 보니 고치기 전 문장이 맞아서 고치기 전 상태로 만들고 이후의 커밋을 삭제하고 싶다.
- 이를 위해 'reset --hard' 명령어를 사용하였다.
- 따라서, 'reset --hard' 명령어는 과거의 커밋으로 돌아가고 해당 커밋 이후의 이력을 모두 삭제하는 명령어라고 할 수 있다. 그리고 reset 명령어의 자주 사용할 것 같은 또 다른 옵션으로는 ‘reset --soft’ 가 있다. reset --soft 옵션은 head와 branch 만 이동할 뿐 reset하기 전까지 했던 staging area, working directory의 작업은 남겨두어 git commit 을 했을 때 기존 상태로 돌아오게 된다. 따라서 ‘reset --soft’명령어는 과감한 'reset --hard'명령어와 달리 안전하고 신중한 옵션이라 할 수 있다.

![9](https://user-images.githubusercontent.com/80791532/117522680-a417cd80-afef-11eb-83ef-37974ee834b9.PNG)

![10](https://user-images.githubusercontent.com/80791532/117522688-ac700880-afef-11eb-8847-f1dc6c8ef3e0.PNG)

![11](https://user-images.githubusercontent.com/80791532/117522694-b3971680-afef-11eb-9a3c-514ab1879a69.PNG)

## 8. 
