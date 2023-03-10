## 1. WAF

WAF는 웹방화벽이다.

구조를 보면
```
LB --> WAF --> WebServer 순으로 사용자가 LB 도메인을 통해 WAF를 거쳐 WebServer 로 도달하게된다.
```
### 생성과정
먼저 KT Cloud 콘솔에서 WAF 서비스 신청을 한 뒤, WAF메뉴에서 웹 방화벽을 생성한다.

이때 자동으로 포트번호가 부여되는데 추가로 자기가 설정할 포트를 적용하는법은 

![img](/image/WAFport1.png)

```
Server -> Networking 에서 타입이 기본으로 되어있는 IP를 선택 후 접속설정
```
![img](/image/WAFport2.png)

```
접속설정에서 직전에 만들었던 WAF를 선택한 뒤 사설Port / 공인Port를 원하는 포트로 설정한다.
```

## 2. Load Balancer
```
서버에 연결되어 있던 로드밸런서를 선택하고 변경을 클릭 ->
적용 서버 항목에서 기존에 연결되어 있던 서버를 삭제하고
만들어두었던 WAF를 선택하면 위에서 추가해줬던 포트를 선택할 수 있다.
```
![img](/image/WAFlb1.png)
![img](/image/WAFlb2.png)


## 3. WAF 콘솔 설정

WAF와 WebServer의 연동 할 때의 설정은 WAF콘솔에서 할 수 있다.

WAF 콘솔 접속 방법
```
WAF 서비스 항목에서 WAF체크 -> ''' 클릭 -> 콘솔 접속
```
콘솔 초기 ID, Password
```
ID = admin
Password = penta7728
```
![img](/image/WAFcon3.png)
![img](/image/WAFcon4.png)

```
프록시 IP = WebServer IP
```