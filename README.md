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
 1. README 체크 X -> 1. 새로운 로컬 저장소를 생성하고 원격 저장소 연결 방법
 2. $mkdir gitstudy05 – 새 폴더 만들기
 3. $cd gitstudy05
 4. $git init – 저장소 깃으로 초기화     
 5. Initialized empty Git repository in E:/gitstudy05/.git/
 6. $echo “#gitstudy05” >>README.md – 파일 생성
 7. $git add README.md – 스테이지에 등록
 8. $git commit –m“first commit”- 커밋
 9. 기존 저장소를 연결하는 방법
 
## 5.3.2 프로토콜
### 1. Local
 * 서버로 이용시 폴더 경로만 입력
 * $ git remote add 원격저장소별칭 폴더경로
 * 빠른 동작 가능 / 모든 자료가 집중되는 위험성O

## HTTP
깃은 HTTP 방식의 프로토컬 지원
HTTP는 기존 아이디와 비밀번호만으로 접속자를 인증하여 처리
HTTP는 익명으로도 처리할 수 있으며, 계정을 이용하여 처리할 수도 있다.

SSH
깃에서 권장하는 프로토콜
높은 수준의 보안 통신으로 처리
주소 앞에 ‘ssh://계정@주소’처럼 프로토콜 타입 지정
접속시 인증서 사용 – 공개키는 서버에 등록, 개인키는 로컬에 저장
익명 접속X

Git
SSH와 유사하지만 인증 시스템X -> 보안에 취약
