# 깃허브 5장 요약
## 5-1) 서버 저장소 = 원격(remote 저장소)
* 협업 저장소의 중요성  
  * 개발자들이 소스 파일들을 수정, 의도치 않은 충동을 방지!
  * 원격 저장소에 작업 저장함에 따라 어디서든 동기화 가능
  * 깃 주소 공유, 다수의 개발자와 협업에 용이한 이점을 차지

<h3>5-2) 계정 생성과 저장소 생성</h3>
① 회원가입
<img src="https://user-images.githubusercontent.com/114343532/192197446-826faad1-06fc-4e2a-a41b-c3dd0de4573d.png" width="70%" height="70%">
② 정보 입력
<img src="https://user-images.githubusercontent.com/114343532/192197456-2a74e5d4-5c82-4e11-8441-4ee6c3987004.png" width="30%" height="30%">
③ 저장소 생성
<img src="https://user-images.githubusercontent.com/114343532/192197459-6c431d53-e800-4556-b3bb-a746a9f48a66.png" width="70%" height="70%">
④ 저장소 정보 입력
<img src="https://user-images.githubusercontent.com/114343532/192197463-06378ab9-770f-458e-83f8-291085d69254.png" width="30%" height="30%">
⑤ 저장소 생성 확인
<img src="https://user-images.githubusercontent.com/114343532/192197465-8d2dd552-08c1-4d74-ac89-3dba6028309c.png" width="70%" height="70%">

# 5.3 깃허브 연동 및 원격 등록
## 5.3.1 로컬 저장소
 * README 체크 X -> 새로운 로컬 저장소를 생성하고 원격 저장소 연결 방법
 * $mkdir gitstudy05 – 새 폴더 만들기
 * $cd gitstudy05
 * $git init – 저장소 깃으로 초기화     
 * Initialized empty Git repository in E:/gitstudy05/.git/
 * $echo “#gitstudy05” >>README.md – 파일 생성
 * $git add README.md – 스테이지에 등록
 * $git commit –m“first commit”- 커밋
 * 기존 저장소를 연결하는 방법
 
## 5.3.2 프로토콜
### Local
 * 서버로 이용시 폴더 경로만 입력
 * $ git remote add 원격저장소별칭 폴더경로
 * 빠른 동작 가능 / 모든 자료가 집중되는 위험성O

### HTTP
 * 깃은 HTTP 방식의 프로토컬 지원
 * HTTP는 기존 아이디와 비밀번호만으로 접속자를 인증하여 처리
 * HTTP는 익명으로도 처리할 수 있으며, 계정을 이용하여 처리할 수도 있다.

### SSH
 * 깃에서 권장하는 프로토콜
 * 높은 수준의 보안 통신으로 처리
 * 주소 앞에 ‘ssh://계정@주소’처럼 프로토콜 타입 지정
 * 접속시 인증서 사용 – 공개키는 서버에 등록, 개인키는 로컬에 저장
 * 익명 접속X

### Git
 * SSH와 유사하지만 인증 시스템X -> 보안에 취약

## 5.3.3 원격 저장소의 리모트 목록 관리
 * remote 명령어를 사용하여 원격 저장소 관리 + 현재 연결된 목록 확인 및 등록, 취소 작업 가능
 * $ git remote – 원격 저장소의 이름 출력(목록만 확인시 편리)
 * $ git remote –v 이름 + URL 확인

## 5.3.4 주소와 별칭
 * 로컬 저장소에 원격 저장소를 등록하련 서버 주소 필요 
 * 깃허브 같은 저장소 이영시 프로토콜 + 도메인 주소 형태로 되어 있다.
 * 로컬에 서버 저장소를 생성 할 때는 폴더 경로를 사용 가능
 * 별칭 – 긴 서버 URL 문자열을 별칭으로 만들어 사용 가능
 * 대표적인 별칭으로 origin 사용
 
## 5.3.5 원격 저장소에 연결

 * 원격 저장소와 연결하려면 add옵션 사용
 * $ git remote add 원격저장소별칭 원격저장소URL
 * 원격 저장소 추가시 인자 값으로 원격 저장소 URL 같이 입력
 * infoh@hojin MINGW64 /e/gitstudy05(master)
 * $ git remote add origin http://github.com/jinygit/gitstudy05.git - 자신의 서버 주소 입력 infoh@hojin MINGW64 /e/gitstudy05(master)
 * $ git remote –v 원격 저장소 목록 확인
 * origin http://github.com/jinygit/gitstudy05.git (fetch)
 * origin http://github.com/jinygit/gitstudy05.git (push)
 * 원격 저장소와 연결되면 fetch와 push 두 주소를 출력
 * 별칭은 중복선택X

## 5.3.6 소스트리에서 원격 브랜치

 * 원격 저장소를 등록하면 기존 master 브랜치와 local/master 같은 별칭/브랜치가 자동 생성된다

## 5.3.7 별칭 이름 변경과 정보
 * 별칭 이름 변경 $ git remote rename 변경전 변경후
 * 상세 정보 확인 $ git remote show 원격저장소별칭

## 5.3.8 원격 서버 삭제
 * 등록된 원격 저장소 삭제
 * $ git remote rm 원격저장소별칭

## 5-4 서버 전송
 * 지역 저장소와 원격 저장소를 연결시킨 후에는 로컬 저장소의 커밋들을 원격 저장소로 업로드할 수 있다.

## 5-4-1 push: 서버에 전송
 * push : 원격 저장소로 커밋된 파일들을 업로드하는 동작
 * push 명령어를 사용하기 전 미리 작업해 둔 원격 저장소와 연결된 서버 목록을 확인해 본다.
 * $git remote –v : 원격 저장소와 연결된 서버 목록을 확인하는 명령어
<img src="https://user-images.githubusercontent.com/114343532/192238302-3e4f20f5-554a-47c5-a077-beacafbdb7ea.png" width="70%" height="70%">
 * 출력된 결과의 2번째 줄에서 ‘gitstudy05’라는 업로드가 가능한 원격 저장소가 등록된 것과 그 저장소의 별칭은 origin으로 설정된 것을 확인할 수 있다.
 
 * $git push 원격저장소별칭 브랜치이름 : 별칭 이름을 가지는 서버의 master 브랜치에 현재 브랜치를 업로드한다.
 * 브랜치(branch) : 독립적으로 어떤 작업을 진행하기 위한 개념으로 한 시점에서 개발자들이 각자 독립적인 작업 영역(저장소) 안에서 마음대로 소스 코드를 변경할 수 있다.
 * 위 명령어를 사용하여 현재 master 브랜치를 origin 서버로 전송해 본다.
<img src="https://user-images.githubusercontent.com/114343532/192238378-d48e1ea5-b1a9-4ccf-a9f7-2d6b13a4d168.png" width="70%" height="70%">
 * 앞에서 언급한 저장소 ‘gitstudy05’의 별칭 origin을 사용하였고 이를 push 명령어를 이용하여 main 브랜치를 origin이라는 원격 저장소로 전송시켰다.
 
 * 내 깃허브 저장소 gitstudy05를 확인해 보면 서버에 새로운 main 브랜치가 생성이 되고, main 브랜치 안에 있는 소스 코드가 저장소에 그대로 업로드된 것을 볼 수 있다. gitstudy 저장소에는 앞서서 README.md 파일을 커밋했었는데 이 md 파일이 깃허브의 gitstudy05 저장소에 올라가게 된 것이다.
<img src="https://user-images.githubusercontent.com/114343532/192238397-60136e23-5d60-4a52-add8-d9cc8db912d6.png" width="70%" height="70%">
 * 이렇게 원격 저장소에 push하면 main 저장소가 로컬 저장소의 main 브랜치와 서버의 main 브랜치 이렇게 총 2개가 생성이 된다.

## 원격 저장소의 용도
1. 자신의 로컬 저장소를 백업하는 용도
2. 다른 사람과 협업하는 용도
