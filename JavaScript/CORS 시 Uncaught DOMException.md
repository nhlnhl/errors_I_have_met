# CORS 시 Uncaught DOMException
한 페이지에서 본인 인증 팝업창을 띄운 후 팝업창에서 본래 페이지에 위치한 Dom 객체의 값을 수정하려고 할 때, 에러가 일어났다.
```
Uncaught DOMException: Blocked a frame with origin "$팝업창의_도메인" from accessing a cross-origin frame.
```
본래 페이지와 팝업창의 도메인이 같은데 왜 이런 오류가 일어나는지 이해가 안 갔는데, 알고보니 둘의 프로토콜이 상이했다.  
본래 페이지의 프로토콜은 http, 팝업창의 프로토콜은 https...  
아예 다른 도메인 간의 통신의 경우에는 window.postMessage()와 같은 방법을 사용할 수 있다고 한다.
> CORS (Cross-Origin Resource Sharing) : 교차 출처 리소스 공유  
> [CORS Wikipedia URL](https://ko.wikipedia.org/wiki/%EA%B5%90%EC%B0%A8_%EC%B6%9C%EC%B2%98_%EB%A6%AC%EC%86%8C%EC%8A%A4_%EA%B3%B5%EC%9C%A0)
