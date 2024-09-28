# **오픈소스SW개발론**

## Introduction
1. [Week 1-1: 강의 개요](#week1-1-강의-개요-강의계획서)
2. [Week 1-2: 오픈소스소프트웨어 개요](#week1-2-오픈소스소프트웨어-개요)
3. [Week 2-1: 버전 관리 개요](#week2-1-버전-관리-개요)
4. [Week 2-2: Git](#week2-2-git)
5. [Week 2-3: GitHub, Fork, and Pull Requests](#week2-3-github-fork-pull-request)
6. [Week 2-4: Git Advanced Topics](#week2-4-git-advanced-topics)
7. [Week 3: Markdown](#week3-----markdown)

-------------
## Week1-1 강의 개요 (강의계획서)
![Open Source Collaboration](https://raw.githubusercontent.com/kwon5min02/oss_git_example/2da33a7b61c5a66d773494983ac2181bae12080b/%EA%B0%95%EC%9D%98%EA%B3%84%ED%9A%8D%EC%84%9C.png)

-------------
## Week1-2 오픈소스소프트웨어 개요
### **_- 오픈소스소프트웨어_**
* 저작권 소유자가 모든 사람에게 소스 코드를 게시, 사용, 복사, 수정 및 배포할 권리를 부여한 소프트웨어
     
### **_- OSS License_**
* 오픈소스 소프트웨어의 사용, 복제, 수정, 배포 권한의 범위를 지정
* GPL, LGPL, MIT License, BSD License, Apache License, MPL
     
![Image](https://postfiles.pstatic.net/MjAyMzA2MTdfMTM3/MDAxNjg2OTc1NjU0MDE4.VvsoriOi_OSRUA773OeisQLz_gtSUx6Mi6oXPLMEhpog.hajLJIVGr2pO5ClObvtoIGso3ungS1YrL_caCQrMOZ8g.PNG.ljk3815/image.png?type=w3840)

### **_- Commercialization View_**
* Commercial SW (E.g. Windows)
  * Individual License (EULA) (개별 이용허락)
  * Royalty (로열티 지급)
  * Binary only (실행 바이너리만 제공)
  * No reproduction, distribution, and modification (복제, 배포, 수정 불가)
  * Limited terms and purposes (사용 기간과 목적 제한)
  * Protected by Intellectual Property Rights (지적재산권)
* Open Source SW
  * Open Source Lincense (일괄 사전 이용허락)
  * No Royalty (로열티 없음)
  * Source code (소스 코드 제공)
  * Reproduction, distribution, and modification are permitted (복제, 배포, 수정 허용)
  * No limitation on terms and purposes (기간/목적 제한 없음)
  * Protected by Intellectual Property Rights (지적재산권)

### **_- Philosophical View_**
* Free Software
  * Richard Stallman – Creator of GNU Project
  * FSF (Free Software Foundation, 1984~)
  * Copyleft  (No SW patent, No DRM)
* Open Source Software
  * Eric S. Raymond – Author of `The Cathedral and the Bazzar (성당과 시장)'
  * OSI (Open Source Initiative, 1998~)

[강의자료](https://docs.google.com/presentation/d/1HJM_NecZ2YZMin9NEL7-_PbZnj44ahYD/edit#slide=id.p1)
[참고자료](https://drive.google.com/file/d/1IRvsG418jiyQqhjOXMc-maEaL17ypBuw/view)

-------------
## Week2-1 버전 관리 개요
### **_- Motivation_**
* Without version control system(VCS), you
  * Make a single backup copy
  * Add a version number or date, and
  * Use a shared folder so other people can see and edit files together
 
### **_- Version Control System (VCS)_**
* Track your files over time so that you can easily get back to a previous working version
* VCS software
  * CVS, SVN, Mercurial, Darcs, Git
* Repository or Repo (저장소)

### **_- General Actions in VCS_**
(+) Trunk  (in SVN), Branch (in Git) : The location for code in the repo.  
(+) check in  (in SVN), commit (in Git)

* Checkin
  * Check in a file(list.txt) and modify it over time
 
![Image](https://betterexplained.com/examples/ad1_files/basic_checkin.png)
* Checkout and editing
  * Check out, edit, and check in a file(list.txt)
 
![Image](https://miro.medium.com/v2/resize:fit:640/format:webp/0*9I_vCQjQ7mlrZy0V.png)
* Diffs
  * The trunk has a history of changes as a file evolves.

 ![Image](https://i0.wp.com/betterexplained.com/wp-content/uploads/version_control/basic_diffs.png)
* Branching
  * Copy code into a separate folder so we can have a separate history of changes
 
![Image](https://betterexplained.com/wp-content/uploads/version_control/first_branch.png)
* Merging
  * Merge changes from one branch to another
 
![Image](https://hermosodia.wordpress.com/wp-content/uploads/2008/08/merging.png)
* Conflicts
  * When changes overlap like an example below
  * Two options by Sue
    * Re-apply your changes (r4 +Hot Dog)
    * Override their changes with yours (r4 -Cheese, +HotDog) 

![Image](https://i0.wp.com/betterexplained.com/wp-content/uploads/version_control/vcs_conflict.png)
* Tagging
  * Let you tag (label) any revision for easy reference such as ‘Release 1.0’ instead of r4

![Image](https://betterexplained.com/wp-content/uploads/version_control/tagging.png)

### **_- Two Main Types of VCS_**
* 중앙 집중식 VCS (Centralized VCS)
  * 하나의 중앙 저장소가 있으며, 여러 사용자가 이 저장소를 통해 파일을 관리합니다.
  * 모든 변경 사항은 중앙 저장소에 기록됩니다.
  * 사용자는 중앙 저장소에서 파일을 체크아웃하고, 수정 후 다시 체크인합니다.
  * CVS, SVN, Darcs
* 분산형 VCS (Decentralized/Distributed VCS)
  * 모든 사용자가 자신의 로컬 저장소를 소유하며, 별도의 원격 중앙 저장소가 존재합니다. 때로는 여러 개의 원격 중앙 저장소가 있을 수도 있습니다.
  * 각 사용자는 자신의 변경 사항을 로컬에서 작업한 후, 원격 저장소에 푸시(pushing)합니다.
  * 사용자 간의 협업이 용이하며, 오프라인에서도 작업이 가능합니다.
  * 새로운 작업
    * Fork: 다른 사용자의 원격 저장소를 복사하여 자신의 로컬 저장소로 가져오는 작업입니다.
    * Pull Request: 수정한 내용을 원래의 원격 저장소에 병합해 달라고 요청하는 작업입니다.
  * GIT, Mercurial

[강의자료](https://docs.google.com/presentation/d/1y_XxFORFUVf5NVa40FTFmv9MemetVjBj/edit#slide=id.p16)

-------------
## Week2-2 Git
### **_- Introduction to GIT_**
* Linus Torvalds
  * 리누스 토발즈는 리눅스 커널의 개발 협업을 위해 GIT라는 분산형 버전 관리 시스템을 만들었습니다.
* GIT의 주요 개념
1. 작업 공간 (Workspace)
   - 사용자가 현재 작업 중인 파일들을 저장하는 곳입니다.
   - 파일을 수정하고 추가하는 등의 작업을 진행합니다.
2. 인덱스 (Index)
   - 스테이징 영역으로, 다음 커밋에 포함될 파일들을 준비하는 곳입니다.
   - _git add_ 명령어를 통해 변경된 파일이 이 인덱스에 추가됩니다.
3. 로컬 저장소 (Local Repository)
   - 사용자가 자신의 컴퓨터에 저장한 파일로, 커밋된 변경 사항이 저장됩니다.
   - 모든 커밋 기록은 이 로컬 저장소에 보존됩니다.
4. 원격 저장소 (Remote Repository)
   - 다른 사용자와 공유하기 위해 파일을 푸시(push)하는 중앙 저장소입니다.
   - _git push_ 명령어를 사용하여 로컬 저장소의 변경 사항을 원격 저장소에 전송합니다.



![Image] (그림.png)

-------------
## Week2-3 Github, fork, pull request
* 이런내용
  > 그런데 이런거
* 저런내용
  > 그런데 저런거

## Week2-4 Git: Advanced topics


-------------
## Week3     Markdown
* 이런내용
* 저런내용
