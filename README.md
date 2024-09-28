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
* **Commercial SW (E.g. Windows)**
  * Individual License (EULA) (개별 이용허락)
  * Royalty (로열티 지급)
  * Binary only (실행 바이너리만 제공)
  * No reproduction, distribution, and modification (복제, 배포, 수정 불가)
  * Limited terms and purposes (사용 기간과 목적 제한)
  * Protected by Intellectual Property Rights (지적재산권)
* **Open Source SW**
  * Open Source Lincense (일괄 사전 이용허락)
  * No Royalty (로열티 없음)
  * Source code (소스 코드 제공)
  * Reproduction, distribution, and modification are permitted (복제, 배포, 수정 허용)
  * No limitation on terms and purposes (기간/목적 제한 없음)
  * Protected by Intellectual Property Rights (지적재산권)

### **_- Philosophical View_**
* **Free Software**
  * Richard Stallman – Creator of GNU Project
  * FSF (Free Software Foundation, 1984~)
  * Copyleft  (No SW patent, No DRM)
* **Open Source Software**
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

* **Checkin**
  * Check in a file(list.txt) and modify it over time
 
![Image](https://betterexplained.com/examples/ad1_files/basic_checkin.png)
* **Checkout and editing**
  * Check out, edit, and check in a file(list.txt)
 
![Image](https://miro.medium.com/v2/resize:fit:640/format:webp/0*9I_vCQjQ7mlrZy0V.png)
* **Diffs**
  * The trunk has a history of changes as a file evolves.

 ![Image](https://i0.wp.com/betterexplained.com/wp-content/uploads/version_control/basic_diffs.png)
* **Branching**
  * Copy code into a separate folder so we can have a separate history of changes
 
![Image](https://betterexplained.com/wp-content/uploads/version_control/first_branch.png)
* **Merging**
  * Merge changes from one branch to another
 
![Image](https://hermosodia.wordpress.com/wp-content/uploads/2008/08/merging.png)
* **Conflicts**
  * When changes overlap like an example below
  * Two options by Sue
    * Re-apply your changes (r4 +Hot Dog)
    * Override their changes with yours (r4 -Cheese, +HotDog) 

![Image](https://i0.wp.com/betterexplained.com/wp-content/uploads/version_control/vcs_conflict.png)
* **Tagging**
  * Let you tag (label) any revision for easy reference such as ‘Release 1.0’ instead of r4

![Image](https://betterexplained.com/wp-content/uploads/version_control/tagging.png)

### **_- Two Main Types of VCS_**
* **중앙 집중식 VCS (Centralized VCS)**
  * 하나의 중앙 저장소가 있으며, 여러 사용자가 이 저장소를 통해 파일을 관리합니다.
  * 모든 변경 사항은 중앙 저장소에 기록됩니다.
  * 사용자는 중앙 저장소에서 파일을 체크아웃하고, 수정 후 다시 체크인합니다.
  * CVS, SVN, Darcs
* **분산형 VCS (Decentralized/Distributed VCS)**
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
* **Linus Torvalds**
  * 리누스 토발즈는 리눅스 커널의 개발 협업을 위해 GIT라는 분산형 버전 관리 시스템을 만들었습니다.
    
* **GIT의 주요 개념**
1. **작업 공간 (Workspace)**
   - 사용자가 현재 작업 중인 파일들을 저장하는 곳입니다.
   - 파일을 수정하고 추가하는 등의 작업을 진행합니다.
2. **인덱스 (Index)**
   - 스테이징 영역으로, 다음 커밋에 포함될 파일들을 준비하는 곳입니다.
   - **`git add`** 명령어를 통해 변경된 파일이 이 인덱스에 추가됩니다.
3. **저장소 (Repository)**
   - 프로젝트 파일과 변경 이력이 저장되는 곳입니다.
5. **커밋 (Commit)**
   - 파일 변경 사항을 저장한 이력입니다.
6. **브랜치 (Branch)**
   - 독립적으로 작업할 수 있는 코드의 분기입니다.
7. **로컬 저장소 (Local Repository)**
   - 사용자가 자신의 컴퓨터에 저장한 파일로, 커밋된 변경 사항이 저장됩니다.
   - 모든 커밋 기록은 이 로컬 저장소에 보존됩니다.
8. **원격 저장소 (Remote Repository)**
   - 다른 사용자와 공유하기 위해 파일을 푸시(push)하는 중앙 저장소입니다.
   - **`git push`** 명령어를 사용하여 로컬 저장소의 변경 사항을 원격 저장소에 전송합니다.

![Image](https://raw.githubusercontent.com/kwon5min02/oss_git_example/refs/heads/master/git1.png)

### **_- Introduction to GIT : Workflow_**

![Image](https://raw.githubusercontent.com/kwon5min02/oss_git_example/refs/heads/master/git2.png)

### **_- Git 명령어 정리_**
1. **기본 명령어**
- **`git init`**: 새로운 Git 저장소를 초기화합니다.
- **`git clone <repository>`**: 원격 저장소를 로컬로 복사합니다.
- **`git status`**: 현재 작업 디렉토리의 상태를 확인합니다.
- **`git add <file>`**: 파일을 스테이징 영역에 추가합니다.
- **`git commit -m "<message>"`**: 스테이징된 파일을 커밋합니다. 메시지를 추가합니다.
- **`git push <remote> <branch>`**: 로컬 커밋을 원격 저장소로 푸시합니다.
- **`git pull <remote> <branch>`**: 원격 저장소의 변경 사항을 가져와 로컬 브랜치에 병합합니다.
- **`git fetch <remote>`**: 원격 저장소의 변경 사항을 가져오지만, 자동으로 병합하지는 않습니다.
2. **브랜치 관련 명령어**
- **`git branch`**: 현재 브랜치 목록을 보여줍니다.
- **`git branch <branch-name>`**: 새 브랜치를 생성합니다.
- **`git checkout <branch-name>`**: 다른 브랜치로 전환합니다.
- **`git merge <branch-name>`**: 현재 브랜치에 다른 브랜치의 변경 사항을 병합합니다.
- **`git branch -d <branch-name>`**: 브랜치를 삭제합니다.
3. **변경 이력 확인**
- **`git log`**: 커밋 히스토리를 보여줍니다.
- **`git diff`**: 변경된 내용을 확인합니다.
- **`git show <commit>`**: 특정 커밋의 내용을 보여줍니다.
4. **원격 저장소 관련 명령어**
- **`git remote -v`**: 현재 연결된 원격 저장소를 확인합니다.
- **`git remote add <name> <url>`**: 새로운 원격 저장소를 추가합니다.
5. **충돌 해결 및 기타**
- **`git stash`**: 현재 작업 중인 변경 사항을 임시로 저장합니다.
- **`git stash apply`**: 임시로 저장한 변경 사항을 복원합니다.
- **`git cherry-pick <commit>`**: 특정 커밋의 변경 사항을 현재 브랜치에 적용합니다.

[강의자료](https://docs.google.com/presentation/d/1y_XxFORFUVf5NVa40FTFmv9MemetVjBj/edit#slide=id.p16)
[실습자료](https://drive.google.com/file/d/1zfWu61frN3ZAjJc0luKZIYbAphJze8it/view)

-------------
## Week2-3 Github, Fork, Pull Request
### **_- Github_**
 : GitHub는 Git 버전 관리 시스템을 기반으로 한 웹 호스팅 서비스입니다. 소스 코드 저장소를 관리하고 협업할 수 있는 플랫폼

* **주요 기능**
1. **버전 관리**
   - Git을 기반으로 하여 코드의 변경 이력을 추적하고, 이전 버전으로 쉽게 되돌릴 수 있습니다.
   - 여러 사람이 동시에 작업할 수 있도록 지원합니다.
2. **협업**
   - 팀원들이 동시에 작업할 수 있는 기능을 제공하며, Pull Request를 통해 코드 변경 사항을 제안하고 리뷰할 수 있습니다.
   - Issues 기능을 통해 버그나 작업 요청을 기록하고 관리할 수 있습니다.
3. **Fork와 Pull Request**
   - 다른 사용자의 저장소를 Fork하여 개인적으로 수정할 수 있으며, 수정 후 Pull Request를 통해 원본 저장소에 변경 사항을 제안할 수 있습니다.
4. **README 파일**
   - 프로젝트의 설명서 역할을 하는 README 파일을 작성하여 사용자나 개발자에게 프로젝트에 대한 정보를 제공합니다.
   - 마크다운 형식을 사용하여 서식을 지정할 수 있습니다.
5. **GitHub Actions**
   - CI/CD(지속적 통합 및 지속적 배포) 파이프라인을 구축할 수 있는 자동화 도구입니다.
   - 특정 이벤트(예: Push, Pull Request) 발생 시 자동으로 빌드, 테스트, 배포를 수행할 수 있습니다.
6. **Pages**
   - 정적 웹사이트를 호스팅할 수 있는 기능입니다.
   - GitHub 저장소에서 직접 웹 페이지를 생성하고 배포할 수 있습니다.

### **_- Fork, Pull Request_**
* **fork**
  * Fork는 다른 사용자의 GitHub 저장소를 복사하여 자신의 GitHub 계정에 새로 생성하는 과정입니다.
  * 오픈 소스 프로젝트에 기여하기 위해, 또는 개인적인 실험을 위해 원본 저장소의 독립적인 복사본을 만들 수 있습니다.
  * 사용 방법
    * Fork하기 : GitHub에서 원본 저장소의 오른쪽 상단에 있는 "Fork" 버튼을 클릭합니다.
    * 로컬 클론: Fork된 저장소를 자신의 컴퓨터로 클론합니다.  
      `git clone https://github.com/your-username/repo-name.git`
    * 수정하기: 로컬에서 필요한 수정 작업을 진행합니다.
* **Pull Request**
  * Pull Request는 자신의 Fork에서 변경 사항을 원본 저장소에 병합해 달라고 요청하는 과정입니다.
  * 다른 사용자가 작성한 코드를 리뷰하고 통합하기 위해 사용됩니다.
  * 사용 방법
    * 커밋 : 로컬에서 변경한 내용을 커밋합니다.
      ```
      git add <file>
      git commit -m "변경 내용 설명"
      ```
    * 푸시 : 변경 사항을 자신의 Fork에 푸시합니다.  
      `git push origin main`
    * Pull Request 생성 : GitHub에서 자신의 Fork 저장소 페이지로 가서 "Pull Request" 버튼을 클릭합니다.
    * 비교 및 설명: 원본 저장소와 자신의 브랜치를 비교하고, 변경 사항에 대한 설명을 작성합니다.
    * 제출 : "Create Pull Request" 버튼을 클릭하여 요청을 제출합니다.
    * 리뷰 및 병합: 원본 저장소의 유지 관리자는 Pull Request를 검토한 후, 필요한 경우 피드백을 제공할 수 있습니다. 변경 사항이 승인되면 병합(Merge)을 진행할 수 있습니다.

-------------
## Week2-4 Git: Advanced topics
### **_- Advanced topics_**
1. **브랜치 전략**
   - **Git Flow**
     - 복잡한 프로젝트를 위해 개발된 브랜치 관리 전략입니다.
     - **Master**, **Develop**, **Feature**, **Release**, **Hotfix** 브랜치가 포함됩니다.
   - **GitHub Flow**
     - 간단한 브랜치 전략으로, 지속적인 배포에 적합합니다.
     - **main** 브랜치에서 새로운 기능 브랜치를 생성하고, 작업 후 Pull Request를 통해 병합합니다.

2. **Git Rebase**
   - **설명**
     - 브랜치의 기본 커밋을 변경하는 명령어로, 깔끔한 커밋 히스토리를 유지하기 위해 사용됩니다.
   - **사용 예**
     ```
     git checkout feature-branch
     git rebase main
     ```
  
3. **Git Cherry-pick**
   - **설명**
     - 특정 커밋을 선택하여 다른 브랜치에 적용하는 방법입니다.
   - **사용 예** 
     ```
     git checkout target-branch
     git cherry-pick <commit-hash>
     ```

4. **Git Stash**
   - **설명**
     - 현재 작업 중인 변경 사항을 임시로 저장하고, 작업 디렉토리를 깨끗하게 만드는 명령어입니다.
   - **사용 예**
     - 변경 사항을 스태시로 저장  
    `git stash`
     - 마지막으로 저장한 스태시를 적용  
    `git stash apply`
     - 스태시 목록 보기  
    `git stash list`

5. **Git Hooks**
   - **설명**
     - 특정 이벤트가 발생할 때 자동으로 실행되는 스크립트입니다. 예를 들어, 커밋 전, 푸시 후 등 다양한 작업을 자동화할 수 있습니다.
   - **용도** 
     - 코드 품질을 유지하기 위해 검사 스크립트를 실행하거나, 커밋 메시지 형식을 검사하는 데 사용할 수 있습니다.

6. **Submodules**
   - **설명**
     - 하나의 Git 저장소 안에 다른 Git 저장소를 포함하는 방법입니다. 모듈화된 프로젝트에서 외부 라이브러리나 다른 프로젝트를 포함할 때 유용합니다.
   - **사용 예**
     - 서브모듈 추가  
    `git submodule add <repository-url>`
     - 서브모듈 업데이트  
    `git submodule update --init --recursive`

7. **Git Configuration**
   - **설명**
     - Git의 동작 방식을 설정할 수 있는 옵션입니다. 사용자 정보, 에디터 설정 등을 포함합니다.
   - **설정 예**
     - 사용자 이름 및 이메일 설정
       ```
       git config --global user.name "Your Name"
       git config --global user.email "you@example.com"
       ```
     - 기본 편집기 설정  
     `git config --global core.editor "code --wait"`

8. **Git LFS (Large File Storage)**
   - **설명**
     - 대용량 파일을 관리하기 위한 Git 확장 기능입니다. Git 저장소의 크기를 줄이고 대용량 파일의 버전 관리를 용이하게 합니다.
   - **사용 예**
     - Git LFS 설치  
    `git lfs install`
     - 특정 파일 형식 추적  
    `git lfs track "*.psd"`
     - Git LFS를 사용하는 파일 추가
       ```
       git add .gitattributes
       git add my-large-file.psd
       ```

-------------
## Week3     Markdown
### **_- Markdown 주요 요소_**
1. 이탤릭체와 볼드체 (Italics and Bold)
   - **이탤릭체**: 글자 양쪽에 밑줄(`_`)을 추가합니다.
     - 예: `_이것_` 
   - **볼드체**: 글자 양쪽에 별표(`**`)를 추가합니다.
     - 예: `**이것**` 
   - 이탤릭체와 볼드체를 한 줄에서 함께 사용할 수 있습니다.

2. 헤더 (Headers)
   - 제목이나 부제를 만들기 위해 해쉬 마크(`#`)를 사용합니다.
   - 헤더 크기에 따라 해쉬 마크 개수를 늘립니다.
     - 예: `# 제목`, `## 부제` 

3. 링크 (Links)
   - **인라인 링크**: 링크할 텍스트를 대괄호(`[]`)로 감싸고, 링크 주소를 소괄호(`()`)로 감쌉니다.
     - 예: `[텍스트](링크)`
   - **참조 링크**: 대괄호로 묶은 참조 태그 후, 콜론과 링크 주소를 사용합니다.
     - 예: `[참조]: 링크`

4. 이미지 (Images)
   - 이미지는 앞에 느낌표(`!`)를 추가합니다.
   - 인라인 이미지 링크:
     - 예: `![대체 텍스트](링크)`
   - 참조 이미지는 참조 링크 앞에 느낌표를 붙입니다.

5. 인용문 (Blockquotes)
   - 문장 앞에 캐럿 기호(`>`)를 추가하여 인용문을 만듭니다.
   - 여러 줄에 걸쳐 인용할 경우 각 줄 앞에 캐럿 기호를 추가합니다.

6. 리스트 (Lists)
   - **순서가 매겨지지 않은 리스트**: 각 항목에 별표(`*`)를 추가합니다.
     - 예: `* 항목 1`
   - **순서가 매겨진 리스트**: 항목 앞에 숫자를 추가합니다.
     - 예: `1. 항목 1`
   - 리스트 안에 이탤릭체, 볼드체, 링크를 추가할 수 있으며, 리스트 안에 리스트를 중첩할 수 있습니다.

7. 단락 (Paragraphs)
   - 각 줄 끝에 2번의 공백을 추가하여 줄 나눔을 할 수 있습니다. 
   - 일반적인 용도는 리스트 내에서 단락을 포맷하는 것입니다.

[강의자료](https://docs.google.com/presentation/d/11d0XT3i64ivf4vmhGgUWDEggpkgVFZwF/edit#slide=id.g15ac5e1ffbe_0_24)
