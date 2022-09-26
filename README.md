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

원격 저장소를 등록하면 기존 master 브랜치와 local/master 같은 별칭/브랜치가 자동 생성된다

## 5.3.7 별칭 이름 변경과 정보
 * 별칭 이름 변경 $ git remote rename 변경전 변경후
 * 상세 정보 확인 $ git remote show 원격저장소별칭

## 5.3.8 원격 서버 삭제
 * 등록된 원격 저장소 삭제
 * $ git remote rm 원격저장소별칭
