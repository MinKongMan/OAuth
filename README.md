# OAuth

OAuth란? 
토큰 기반의 인증 및 권한을 위한 표준 프로토콜.
OAuth와 같은 인증 프로토콜을 통해 유저의 정보를 페이스북, 구글, 카카오 등의 서비스에서 제공받을 수 있고
이 정보를 기반으로 어플리케이션 사용자에게 로그인이나 다른 여러 기능들을 손쉽게 제공할 수 있다.

	개발자는 Facebook등과 같은 서비스에게 accessToken을 발급 받음(id 비밀번호 대신에 받음)
	accessToken을 활용해 소셜 서비스에 접근해 데이터를 가져오고 수정 조회 등의 작업을 함
  
mine : Client 내가 만든 서비스

User : Resource Owner Their라는 서비스에 회원가입이 되어있는 상태

Their : Resource Server(Facebook등)

1. Client가 Resource Server의 서비스를 이용하기 위해 사전에 등록을 해야함.
	보통 Client ID, Client Secret, Authorized redirect URIs를 받음
				Resource Server가 Authorized code를 전달해줄 때 해당 주소로 전달함

2. Resource Owner가 어플리케이션을 이용할 때 Resource Server를 사용할 때가 있다.(ex 페북에 글을 게시)
	그럴 때 Client가 Resource Owner에게 facebook으로 로그인하기 등 버튼이 있는 화면을 띄움
	버튼에는 링크가 있는데, https://~/?clientid=~&scope=B,C&redirect_uri=~ 이런 형식의 링크를 담고 있음.
	클라이언트 ID, 사용하고자하는 기능, redirect주소 3가지
	위 주소로 Resource Owner가 Resource Server로 접속을 하게 되면 Server가 Owner가 로그인 되어있는지 아닌지 판단
	만약 안 되어 있으면 로그인 하라는 창 줌
	로그인 성공 시 clientid와 같은 값이 있는지 Resource Server가 판단
	그리고 같은 아이디면 redirect_uri 값을 비교해서 다르면 작업 중단 
	같다면 Resource Owner에게 Scope에 해당되는 권한을 Client에게 부여할 것인지를 확인하는 메세지를 보냄
	허용한다면 Resource Server는 user id:1(Owner는 user id 1이라 가정)은 Scope B,C를 사용하는데 동의하였다라는 내용을 저장
