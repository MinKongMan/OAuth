# OAuth

OAuth란? 토큰 기반의 인증 및 권한을 위한 표준 프로토콜.
	OAuth와 같은 인증 프로토콜을 통해 유저의 정보를 
	페이스북, 구글, 카카오 등의 서비스에서 제공받을 수 있고
	이 정보를 기반으로 어플리케이션 사용자에게 로그인이나 다른 여러 기능들을 손쉽게 제공할 수 있다.

	개발자는 Facebook등과 같은 서비스에게 accessToken을 발급 받음(id 비밀번호 대신에 받음)
	accessToken을 활용해 소셜 서비스에 접근해 데이터를 가져오고 수정 조회 등의 작업을 함
  
mine : Client 내가 만든 서비스
User : Resource Owner Their라는 서비스에 회원가입이 되어있는 상태
Their : Resource Server(Facebook등)

1. Client가 Resource Server의 서비스를 이용하기 위해 사전에 등록을 해야함.
	보통 Client ID, Client Secret, Authorized redirect URIs를 받음
				Resource Server가 Authorized code를 전달해줄 때 해당 주소로 전달함
