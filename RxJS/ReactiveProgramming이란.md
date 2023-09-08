## Reactive Programming이란

- In computing, reactive programming is a declarative programming paradigm concerned with data streams and the propagation of change
- 데이터 스트림 및 변경 사항의 전파에 관한 선언적 프로그래밍 패러다임

<img width="766" alt="image" src="https://github.com/mimseong/Study/assets/50068946/2f1eff48-2929-428f-9e3f-2637cfcf3584">

- Observable은 data stream이라는 추상적인 개념을 구현한 구현체
- Observable을 구독하고 Observable에서 다양한 값들이 발생하면 이를 받아서 어떤 행동을 취한다

## 구성 요소

![image](https://github.com/mimseong/Study/assets/50068946/9a4aae29-496c-4f9c-a7b1-d5fafd7cea15)

- Observable
- Operator
- Observer

## 왜 ReactiveX를 쓰는가

- 시간의 흐름, 사용자의 동작, 네트워크 요청 결과까지 스트림으로 만들어서 처리
- 시간의 흐름 속에 생겨나는 이 값들을 마치 리스트나 배열처럼 다룰 수 있다
