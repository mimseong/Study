# Observable

## 생성방법

![image](https://github.com/mimseong/Study/assets/50068946/9a4aae29-496c-4f9c-a7b1-d5fafd7cea15)

- Observable은 lazy하다
- 누군가 구독을 해야 발행을 시작한다

### 배열 관련 Observable

- of: 인자들을 발행하는 Observable 생성
- from: 리스트로부터 Observable 생성
- range: 지정된 범위 내에서 연속적인 숫자를 발행하는 Observable 생성

```
const { of, from, range, generate } = rxjs

const obs1$ = of(1, 2, 3, 4, 5)
const obs2$ = from([6, 7, 8, 9, 10])
const obs3$ = range(11, 5)
const obs4$ = generate(
  15, x => x < 30, x => x + 2
)

obs1$.subscribe(item => console.log(`of: ${item}`))
obs2$.subscribe(item => console.log(`from: ${item}`))
obs3$.subscribe(item => console.log(`range: ${item}`))
obs4$.subscribe(item => console.log(`generate: ${item}`))
```

### 시간 관련 Observable

- interval: 지정된 시간 간격마다 일련의 숫자를 발행하는 Observable 생성
- timer: 숫자 0을 발행하기 전 지정된 시간을 기다리는 Observable 생성

```
const { interval, timer } = rxjs

const obs1$ = interval(1000)
const obs2$ = timer(3000)

// 1초 마다 실행
obs1$.subscribe(item => console.log(`interval: ${item}`))
// 3초 뒤에 실행
obs2$.subscribe(item => console.log(`timer: ${item}`))
```

### 이벤트 관련 Observable

- 주어진 이벤트 타겟으로부터 특정 타입의 이벤트를 발행하는 Observable 생성

```
<input id="myInput" type="text"/>
```
```
const { fromEvent } = rxjs
// 클릭할 때마다 이벤트 발생
const obs1$ = fromEvent(document, 'click')
const obs2$ = fromEvent(document.getElementById('myInput'), 'keypress')

obs1$.subscribe(item => console.log(item))
obs2$.subscribe(item => console.log(item))
```

### Ajax Observable

- ajax: ajax request로부터 발행하는 Observable 생성

```
const { ajax } = rxjs.ajax

const obs$ = ajax(`http://127.0.0.1:3000/people/1`)

obs$.subscribe(result => console.log(result.response))
```

## 직접 만드는 Observable

```
const { Observable } = rxjs

const obs$ = new Observable(subscriber => {
  subscriber.next(1)
  subscriber.next(2)
  subscriber.next(3)

  // 값을 다 발행한 뒤에는 compelte를 실행하여 메모리 해제 
  subscriber.complete()
})

obs$.subscribe(item => console.log(item))
```


