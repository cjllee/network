## 토큰기반인증방식
토큰기반 인증방식은 state를 모두 토큰 자체만으로 처리하며 토큰을 처리하는 한 서버를 두고 다른 컨텐츠를 제공하는 서버는 모두 stateless하게 만들자는 이론이 담긴 방식입니다. 왜 토큰을 관리하는 서버는 따로 두어야 할까요?

이는 여러개의 서버를 운용한다라고 했을 때 토큰기반인증 + A도메인을 처리하는 서버로 구축할 경우 A도메인에서 에러가 발생이 되면 인증에 관한 기능이 마비되고 이는 B, C, D 등의 도메인 기능이 연쇄적으로 마비될 수 있기 때문입니다. 토큰은 주로 JWT토큰이 활용됩니다.

1. 인증로직 >> JWT토큰생성(access 토큰, refresh 토큰)
2. 사용자가 이후에 access 토큰을 HTTP Header - Authorization 또는 HTTP Header - Cookie에 담아 인증이 필요한 서버에 요청해 원하는 컨텐츠를 가져옵니다.

![](https://velog.velcdn.com/images/cjllee/post/42cf7297-0b01-4f35-a199-d81e4a6a3831/image.png)

## JWT란?
JWT는 JSON Web Token을 의미하며 헤더, 페이로드, 서명으로 이루어져 있으며 JSON 객체로 인코딩되며 메시지 인증, 암호화에 사용됩니다.

![](https://velog.velcdn.com/images/cjllee/post/51fb1601-ce24-472b-8f7b-d419c3d3c83f/image.png)


Header
- 토큰 유형과 서명알고리즘, base64URI로 인코딩 됩니다.

Payload
- 데이터, 토큰 발급자, 토큰 유효기간, base64URI로 인코딩 됩니다.

Signature
- (인코딩된 header + payload) + 비밀키를 기반으로 헤더에 명시된 알고리즘으로 다시
생성한 서명값.

### 장점
1. 사용자 인증에 필요한 모든 정보는 토큰 자체에 포함하기 때문에 별도의 인증 저장소가 필요 없습니다.
2. 다른 유형의 토큰과 비교했을 때 경량화되어있습니다. SAML(Security Assertion Markup Language Tokens)이란 토큰이 있지만 이에 비해 훨씬 경량화되어있음.
3. 디코딩했을 때 JSON이 나오기 때문에 JSON을 기반으로 쉽게 직렬화, 역직렬화가 가능하다.


### 단점
1. 토큰이 비대해질 경우 당연히 서버과부화에 영향을 줄 수 있습니다.
2. 토큰을 탈취당할 경우 디코딩했을 때 데이터를 볼 수 있습니다.
