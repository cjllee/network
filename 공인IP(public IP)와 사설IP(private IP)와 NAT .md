IP주소의 부족을 공인IP(public IP)와 사설IP(private IP)로 나누고 중간에 NAT이라는 기술을 통해 해결합니다.
NAT (Network Address Translation)는 패킷이 트래픽 라우팅 장치를 통해 전송되는 동안 패킷의 IP주소를 변경, IP 주소를 다른 IP 주소로 매핑하는 방법입니다.

![](https://velog.velcdn.com/images/cjllee/post/fdef3267-329d-44fd-898e-12e6b8a5e18c/image.png)
NAT을 통해 내부 네트워크 IP가 노출되지 않는다는 점 등이 장점입니다.

### 공유기와 NAT
실생활에서 인터넷 회선 하나를 개통하고 보통 공유기를 써서 wifi를 만들곤 하는데 이 때 여러 대의 호스트가 하나의 공인 IP 주소를 사용하여 인터넷에 접속하게 됩니다.
