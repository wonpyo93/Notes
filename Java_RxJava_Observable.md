# RxJava

## Observable의 팩토리 함수
> 여러 가지가 있지만 **just()**, **create()**, **fromXXX()** 를 알아보자.
> **just()** 와 **create()**의 가장 큰 차이점은 onNext, onComplete, onError의 행동 방식이라는 것만 먼저 이해하자.

### just()
> just()는 가장 간단한 생성 방식이라 **onNext()**, **onComplete()**, **onError()**가 자동으로 호출된다.
> 데이터를 만드는 순간 바로 호출된다는 것이다.
> 이걸 다르게 하고싶으면 **map()**을 따로 추가해줘야한다.
> 예시)
<pre><code>
//그대로 발행
Observable.just(1, 2, 3)
        .subscribe(System.out::println);

// 변환하고 싶은 경우
Observable.just(1, 2, 3)
        .map(x -> x * 10)
        .subscribe(System.out::println);

[실행결과]
1
2
3

[실행결과]
10
20
30
</code></pre>

### create()
> create()는 just()와 달리 **onNext()**, **onComplete()**, **onError()** 를 언제 써야하는지 설정해 줘야한다.
> 예시)
<pre><code>
Observable.create(emitter -> {
    emitter.onNext(1);
    emitter.onNext(2);
    emitter.onNext(3);
    emitter.onComplete();
}).subscribe(System.out::println);

[실행결과]
1
2
3
</code></pre>

### justXXX()
> justXXX()는 justArray, justAction, justCallable, justCompletable 등등 여러가지가 존재한다.
> create대신 just를 쓰는 이유는 여러 데이터를 사용해야 하기 때문이다.
> 위의 create() 코드를 보면 1, 2, 3 이렇게 따로 따로 보내야 하지만
> justArray()의 경우 array를 한번에 보낼 수 있게 된다.
> 예)
<pre><code>
Integer [] array = {1, 2, 3, 4, 5};
Observable.fromArray(array)
        .subscribe(System.out::println);
</code></pre>
> 또 중요한 fromXXX() 중에 fromIterable()이 있는데,
> Iterable Interface가 있는 Class 자체를 Observable로 변환할 수 있다.
> ArrayList, Vector, 나중에는 json으로 뽑아내기 위한 data class도 observable로 뽑아낼 수 있게 된다.
> 예)
<pre><code>
ArrayList<Integer> arrayList = new ArrayList<>();
arrayList.add(1);
arrayList.add(2);
arrayList.add(3);
Observable.fromIterable(arrayList)
        .subscribe(System.out::println);
</code></pre>

##### 출처: 
> [1](https://4z7l.github.io/2020/12/03/rxjava-2.html)
