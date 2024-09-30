WSAEventselect 모델을 사용한 nonblocking socket

WSAevent를 사용하여 select 모델과 비슷한 방식으로 동작하는 것이 특징

but select모델은 반복문이 계속돌면서 전체초기화를 해주어야했지만 WSAEvent는 event알림 signal만 확인 후 초기화 해주면 된다.

장점 - select모델은 반복문이 계속돌면서 전체초기화를 해주어야했지만 WSAEvent는 event알림 signal만 확인 후 초기화 해주면 된다.

단점 -  select 모델과 마찬가지로 WSAWaitForMultipleEvents에서 받는 이벤트 개수 인자가 너무작다. 
        maxvalue 가 WSA_MAXIMUM_WAIT_EVENTS가 64이다. SELECT모델과 마찬가지로 그 이상의 숫자를 등록할려면 반복문을 또 써야하는 것이다. 
        64개정도 640개를 등록해야한다면 10번 반복문 돌려야한다.
