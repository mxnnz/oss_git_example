# **오픈소스SW개발론**

### Introduction

-------------
### Week1-1 강의 개요 (강의계획서)
* **오픈소스소프트웨어**
  1. 오픈소스소프트웨어 개발을 위한 기본 개념과 도구, 특히 소스 코드 버전 컨트롤과 패키지 관리, 프로젝트 빌드 중점으로 배움  
  2. 애자일 기반 소프트웨어 개발 방법인 짝 프로그래밍, 테스트 주도 개발, 행위 주도 개발, 클라우드 기반 데브옵스 공부  
  3. 새로운 소프트웨어 개발 환경 및 도구를 스스로 배우는 태도 배움을 목적으로 함. 새로운 추세의 컴퓨팅 환경을 빠르게 적응해 협력적인 소프트웨어 개발을 주도할 수 있는 능력 배움  
  
* **수업목표**  
  * 컴퓨팅 사고 - 함수형 프로그래밍 언어 스타일 익힘
  * 융합 - LLM/ChatGPT를 새로운 프로그래밍을 배우는데 활용
  * 글로컬 - _Basic concepts and tools for open-source software development_  
 -_Attitude to self-learn new SW tools and environments_  
  -_Basic functional programming, Haskell_



-------------
### Week1-2 오픈소스소프트웨어 개요
* GitHub - 오픈소스 소프트웨어에서 빠질 수 없는 사이트 


[GitHub Octoverse](https://octoverse.github.com/)  
-> 최근에 어떤식으로 소프트웨어 개발이 이루어져 있는지, 어떤 언어를 많이 쓰는지 등 오픈소스의 현황을 볼 수 있는 매년 올라오는 리포트  
Ex) 2018년 Top 10 오픈소스 프로젝트
1. Microsoft/vscode  
2. facebook/react-native  ....  
..  

* OSS in Top SW Companies  
  * Facebook  
  * Google
  * Twitter
  * Uber
  * AWS(Amazon Web Service)
  * Microsoft
  * KaKao Tech
  * Naver  

**OSS의 정의**  
저작권을 가지고 있는 사람이 소스코드를 게시, 사용, 복사, 수정 및 배포할 권리를 부여한 소프트웨어  
**OSS 라이센스**  
오픈소스 소프트웨어의 사용, 복제, 수정, 배포 권한의 범위를 지정  


![OSS](image-4.png)  
**철학적관점**  
_Free Software_ VS _Open Souce Software_  
* Free Software- **Richard Stallman** 소스는 특허나 권리를 가지고 있으면 안된다 주장  
--> 자유소프트웨어 (공짜X)

* Open Souce Software- **Eric S. Raymond** 자유로운 재배포 주장  
-> 회사에서 독점적으로 소스를 가지고 있으며 돈을 주고 파는 경우는 오픈소스소프트웨어가 아니다! 맞다! 이런 차이점이라고 볼 수 있음  


**오픈소스소프트웨어 라이센스**  
Ex)GPL(GNU General Public License)  
-> 소스공개의 의무
  * LGPL(GNU Lesser General Public License)  
  -> 좀 더 완화된 GPL, 링크한 경우는 소스공개 의무 없음  

  .... 등등  

  ![License](image-5.png)  

  **라이센스 위반사례**  
  제품: 유무선 공유기  
  적발기관: FSF  
  위반내용: Broadcom으로부터 제공받은 리눅스 소스를 공개하지 않음!  
  --> FSF 요구에 소스 공개함 


-------------
### Week2-1 버전 관리 개요
**Version control system(VCS)**  
이전 작업 버전으로 돌아갈 수 있도록 관리하는 것 앞으로 올 수도 있음  

**VCS software**
* CVS - 초창기에 사용
* SVN - 옛날에 많이 사용
* Mercurial
* Darcs
* Git - 요즘에 거의 Git 사용  

_Repository_ or _Repo_ - "저장소"  

* checkin(commit)- 버전 관리하는 저장소, 내가 작업한 것을 보내는 것  
* checkout(fetch/pull)- 저장소에서 가져오는 것  
* diff(Branch)- 버전간에 비교 (가져온것과 비교)  
* Branching- 코드 분기  
* Merging- 두 버전 병합  
* **Conflicts**- 충돌이 발생했을 때 알려주는게 VCS가 하는 일  
* Tagging- 식별을 위해 태그(레이블)을 붙이는 것

![Real-Life Example](image.png)  

**Two Main Types of VCS**  
1. Centralized VCS (중앙집중형)- 하나의 저장소를 가지고 있고 여러사람이 달라붙어 사용  
ex) SVN  
2. Decentralized VCS (분산형태)- 내 저장소가 따로 있고 원격 서버에 원격 저장소가 있음 분산 방식의 버전 관리  
ex) GIT
 



-------------
### Week2-2 Git
**GIT**  
* '리누스 토발즈' - git개발  
* 분산형 버전 관리 시스템
* 저장소를 포함해서 네가지 관리 영역이 있음  
  * Workspace: 작업중인 파일  
  * index(staged): 내가 앞으로 관리할 파일들의 목록  
  * Local repository: 로컬 저장소에 커밋된 파일  
  * Remote repository: 원격 저장소에 푸쉬된 파일


* **git clone**- Remote Computer에서 Local Computer까지 가져오는 명령어  
* **git add**- 변경사항을 스테이징 영역에 추가  
* **git commit**- 추가한 것을 Local Repository까지 가져옴  
* **git commit-a**- add와 commit을 한꺼번에 하고 싶을 때 사용  
* **git push**- Local 저장소에 있는 것을 Remote 저장소로 옮김 --> 내가 작업한 내용을 다른사람들이 가져갈 수 있도록 하는 것!  

## **반대로!**  
* **git fetch**- 다른사람이 푸쉬해논 내용을 내 원격 저장소로 가져옴  
* **git merge**- 병합함! 워크스페이스로 가져오는 것  
* **git pull**- fetch와 merge를 한꺼번에 함  
* **git diff HEAD**- 원격 저장소에 가져온걸 워크스페이스랑 비교  
* **git diff**- 스테이지에 있는 것과 비교  

**fork** 와 **pull request**  
![GIT](image-2.png)


-------------
### Week2-3 Github, fork, pull request
* fork : 오픈소스의 Remote 저장소를 내 Remote 저장소로 가져오는 것  
* pull request : 내가 수정한 것을 merge해달라고 다시 오픈소스 Remote 저장소로 보내는 것  

 _github에서 fork 버튼 누르기_
> git clone (github에서 fork한 후 github 주소)

> copy con 224619(학번).txt

> dir 224619.txt

> git commit -a -m "add a new file"

> git push origin master

--> fork하고 수정 후에 내 Remote 저장소에 올리는 것 까지 하는 코드  
_이후 github에서 pull request 하기!_

![fork, pull request](image-3.png)


[My Github Blog](https://github.com/mxnnz)

-------------
### Week3     Markdown
**Markdown**  
- 일반 텍스트 편집기를 사용해서 서식 있는 텍스트를 생성하기 위한 경량 마크업 언어  

참조  
* [Wiki](https://en.wikipedia.org/wiki/Markdown)  
* [Markdown tutorial](https://www.markdowntutorial.com/)  
* [Github tutorial](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)  
* [GitHub Flavored markdown spec](https://github.github.com/gfm/)  

**Markdown tutorial**  
* _(문장)_ - 이텔릭체  
* **(문장)** - 볼드체  
* #(문장) - 헤더 (1개부터 6개까지)
등...
![markdown](image-6.png)  
-> 이런식으로 8개의 튜토리얼을 마쳐 언어를 습득할 수 있음!