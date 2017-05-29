# REST
## 1. 정의
### HTTP URI + HTTP Method
REST(Representational State Transfer)

- www와 같은 분산 하이퍼미디어 시스템을 위한 소프트웨어 아키텍쳐의 한 형식 
- 네트워크 아키텍처 원리(자원을 정의하고 자원에 대한 주소를 지정하는 방법)의 모음    
- URI와 HTTP 메소드를 이용해 객체화된 서비스에 접근하는 것



## 2. 특징

### Stateless  
직관적인 객체의 접근으로 서비스를 처리한다. 쿠키/세션 정보가 필요하지 않기 때문에 서비스의 자유도가 높아지며 로드밸런싱 등의 유연한 아키텍쳐의 적용이 가능하다.

- 각 요청간 클라이언트의 Context는 서버에 저장되어서는 안된다.
- 모든 요청은 일회성을 성격을 갖는다. 이전의 요청에 영향을 받지 않아야한다. 


### HTTP URI를 통한 Resource 지정
- 모든 자원은 HTTP URI를 통해 Resource로 표현한다.
- 객체에 대해 유일하고 직관적인 URI를 통해 접근한다. 


anohk.com의 blog의 35번 포스트 정보에 접근하려면 다음과 같은 URI를 사용한다.  
`www.anohk.com/blog/post/35`



> 아래과 같은 방법은 RESTfull한 방법이 아니다.  
`www.anohk.com/blog/post/show/1`


### 자원에 대한 행위는 HTTP Method로 표현한다.
URI를 사용해 자원을 찾고, 이에 대한 명령(CRUD를 명시)을 내린다.  
HTTP가 제공하는 GET/PUT/POST/DELETE 메서드를 이용해 서비스를 제공한다. 

| HTTP Method  | 의미 |
|---|---|
| POST | CREATE |
| GET | RETRIVE |
| PUT | UPDATE |
| DELETE | DELETE |

이외의 추가적인 메서드를 더 제공한다. 

> **PATCH**  
PUT은 해당 자원 전체를 교체하는 의미를 갖고있다. 자원의 일부만 변경하기 위해서 **PATCH** 라는 메서드를 사용한다. 이는 update 이벤트에서 PUT 메서드보다 의미적으로 적합하다는 평을 받고있다.


## 3. 장점
- 기존의 웹 인프라를 그대로 이용할 수 있다.(방화벽, 장비 요건 불필요)
- Open API를 제공하기 쉽다.
- 언어, 플랫폼에 중립적이다.
- 각각의 요청에 독립적이다.(세션, 쿠키 불필요)
	
## 4. 단점
- 정확한 표준이 없기 때문에 관리가 어렵다. 
- CRUD만으로 분류할 수 없는 작업이 존재한다.





	