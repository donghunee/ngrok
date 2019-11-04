# Ngrok

여러분 ec2에 올리기 어렵다면 ngrok을 사용해보세요~!!! 클라이언트와 통신할때 테스트 용도로 자주 사용하는 프로그램입니다.

공식 페이지에서 ngrok은 NAT와 방화벽 뒤에 있는 로컬 서버를 안전한 터널을 통해 공개 인터넷에 노출시켜 주는 도구라고 설명되어 있습니다.

즉, 포트 포워딩과 같은 네트워크 환경 설정 변경없이 로컬에 실행중인 서버를 안전하게 외부에서 접근 가능하도록 해주는 도구입니다.

---

## 설치 방법 

- mac  
brew를 통해 설치합니다.

```
brew update & brew cask install ngrok
```

- window  
[ngrok 공식홈페이지](https://dashboard.ngrok.com/get-started)에서 다운로드 및 설치

---
## 사용 방법

만약 여러분이 local 서버를 3000번 포트로 열었다고 가정해 봅시다.  
ex) localhost:3000 

하지만 클라이언트 (Android, IOS)에서 저희 local서버에는 접근을 못하겠죠?? 

그때 외부에서 접근할 수 있게 만드는 것이 바로 ngrok의 역할입니다.

아까 3000번 포트를 열었으니 터미널을 열고 다음과 같이 입력해봅니다.

```
ngrok http 3000
```
그럼 다음과 같은 화면이 나옵니다.

```
ngrok by @inconshreveable                                                                                                                                                     (Ctrl+C to quit)
                                                                                                                                                                                              
Session Status                online                                                                                                                                                          
Session Expires               7 hours, 59 minutes                                                                                                                                             
Update                        update available (version 2.3.35, Ctrl-U to update)                                                                                                             
Version                       2.3.34                                                                                                                                                          
Region                        United States (us)                                                                                                                                              
Web Interface                 http://127.0.0.1:4040                                                                                                                                           
Forwarding                    http://6541563d.ngrok.io -> http://localhost:3000                                                                                                               
Forwarding                    https://6541563d.ngrok.io -> http://localhost:3000                                                                                                              
                                                                                                                                                                                              
Connections                   ttl     opn     rt1     rt5     p50     p90                                                                                                                     
                              0       0       0.00    0.00    0.00    0.00                                                                                                                    
                                                                                                                                                                                              
                                                                                 
```

저희는 **https://6541563d.ngrok.io** 이것을 클라이언트에게 알려주면 저희 로컬 서버에 접근할 수 있답니다!!!

ec2 서버 설정이 힘드신분들은 요걸 사용해서 호스팅하는데 시간을 줄여보도록 해봐요!! 화이팅~~!!

본 방법은 테스트 할때 쓰이는 것이므로 정식 서비스를 출시한다면 ec2를 사용해야합니다.
