## REST API

### REST API 란?

1. URI를 통해 자원을 지정
2. HTTP 메서드 : 자원에 대한 행위 표현
   사용자라는 자원을 통해서 CRUD 작업을 하고 싶은 경우 /user 와 같은 uri로 사용자를 지정하고 POST/GET/PUT/DELETE를 통해 사용자에 대한 생성, 조회, 수정, 삭제를 처리하는 것

#### REST API를 만든 Fielding의 REST API란?

- 개념적인 대상 (ex. 문서, 이미지, 자원들의 집합, 실존하는 대상 등)

fielding은 자원을 객체로 생각하였다.

- 상태는 변화가능! => 변하지 않는 식별자 필요!
  자원은 시간이 지남에 따라 없었던 것이 생성되고 변화되어 파괴되어 없어집니다. 그렇기 떄문에 이러한 특정한 객체를 식별하기 위해서는 해당 객체의 현재 상태를 보는 것만으로는 부족하다. 개별객체의 언제나 변하지 않는 불변값 즉! 고유한 식별자를 부여해줘야 한다.

"URI를 통해 자원을 식별해야 한다!"
서버의 개별 자원에대한 고유한 식별자로 URI를 사용해야한다.

2. 표현을 통한 자원에 대한 조작

- 표현 : 특정한 상태의 자원에 대한 표현
  자원에 대한 데이터는 다양한 방식으로 표현될 수 있다.
  사용자란 다음과 같은 예로 표현될 수 있다.
- 자원은 다양한 방식으로 표현 가능
- 예 : 문서, 파일, HTTP 메세지 엔티티 등

<pre>
REST : 자원에 대한 표현 전송

REpresentational State Transfer
표현된 (자원의) 상태 전송
- 자원의 현재상태 
- 자원의 기대되는 상태

uri시간에 따라 변화할수 있다.
특정시점에 자원이 지니고 있는 상태를 특정한 형식으로 표현하고 그 표현을 클라이언트와 서버가 서로에게 전송하는 것이라고 말할수 있다.
</pre>

3. 자기 서술적 메세지
   메세지는 스스로에 대해 설명해야 한다!
   클라이언트와 서버사이를 오가는 메세지는 그 자체로 스스로에 대해 충분히 설명할 수 있어야 한다.
   누구에게 설명하는가 ? 메세지를 읽는 주체들에게 설명해야한다.

클라이언트와 서버 사이에는 수많은 컴포넌트들이 있다.
클라이언트의 보낸 요청이 네트워크 어딘가에 특정하여 정확하게 도착하고 서버의 응답메세지가 다시 클라이언트에 다시 도달할수 있는 것은 바로
이 컴포넌트들은 순차적인 도움덕분에 가능하다. 이떄 클라이언트와 서버에서 보내는 응답요청 메세지들은 컴포넌트들에게 자신을 어떻게 처리해야하는지에 대해 제대로 설명해야한다는 것이 제약조건의 의미이다.
