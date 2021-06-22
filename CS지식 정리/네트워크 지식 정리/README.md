# 네트워크 지식 정리



### 동기식 비동기식

- Synchronous(동기식) 통신
  - Request를 보낸 Thread는 Response가 도착하기 전까지는 아무것도 하지 못하는 Block 상태가 됨
  - 요청과 응답값의 순서를 보장
  - 응답이 올 때까지 기다려야하는 비 효율성
- Asynchronous(비동기식) 통신
  - Request를 보낸 Thread는 다른 일을 할 수 있음. Non Block 상태
  - 요청과 응답에 대한 순서를 보장하지 않음 -> 먼저 보낸 요청이 뒤에 보낸 요청보다 응답이 늦을  수 있다.
  - 

