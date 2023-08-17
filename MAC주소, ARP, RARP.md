## MAC

IP 주소(Internet Protocol address)는 논리적 주소이며 컴퓨터 네트워크에서 장치들이 서로를 인식하고 통신을 하기 위해서 사용하는 특수한 번호이며 IP를 기반으로 통신한다고도 하지만 사실상 그 밑에 물리적 주소인 MAC 주소를 통해 통신합니다.

MAC주소
MAC 주소(Media Access Control Address)는 네트워크 인터페이스에 할당된 고유 식별자이며 보통 장치의 NIC에 할당됩니다.
![](https://velog.velcdn.com/images/cjllee/post/39ff2a85-782e-4743-a223-08072d47cf7a/image.png)
48비트로 이루어져있으며 24비트의 OUI와 24비트의 UAA로 이루어져있습니다.
- OUI : IEEE에서 할당한 제조사 코드
- UAA : 제조사에서 구별되는 코드

## 실습
```
ipconfig/all
```
![](https://velog.velcdn.com/images/cjllee/post/66b3ec8c-3e17-45c2-826a-af64180df922/image.png)
참고로 MAC주소는 보통은 유일하지만 유일하지 않을 수도 있습니다. 실수 또는 의도적으로 UAA를 중복되게 만들 수도 있습니다. 이 때 동일 네트워크에서만 중복되지 않으면 문제없긴 합니다. 또한 NIC에 고정된 MAC주소를 변경할 수는 있으나 하지 않는 것을 권장하며 하는 것 자체를 어렵게 한 OS도 있습니다.

### IEEE
IEEE(Institute of Electrical and Electronics Engineers)는 전기/전자/전산 분야의 국제 기구 및 학회이다. 관련 전문가들이 합병해서 창설한 국제조직이며, 관련 기술 공유와 표준 정의 등의 활동을 합니다.

### PC의 NIC
![](https://velog.velcdn.com/images/cjllee/post/35ab79bd-d8da-44de-9ca4-d79cee582cb4/image.png)

### ARP와 RARP
이 MAC주소는 ARP를 통해 파악이 가능합니다.
ARP를 통해 논리적 주소인 IP 주소를 물리적 주소인 MAC 주소로 변환합니다. 이와는 반대로 RARP를 통해 물리적 주소인 MAC 주소를 논리적 주소인 IP 주소로 변환하기도 합니다.

![](https://velog.velcdn.com/images/cjllee/post/111073fe-f9c2-4236-b8b4-18be39ad7a07/image.png)

### ARP의 과정
1. 해당 IP주소에 맞는 MAC주소를 찾기 위해 해당 데이터를 “브로드캐스팅”을 통해 연결된 네트워크에 있는 장치한테 모두 보냅니다.
2. 맞는 장치가 있다면 해당 장치는 보낸 장치에게 유니캐스트로 데이터를 전달해 주소를 찾게 됩니다.
