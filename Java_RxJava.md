# RxJava


>  ReactiveX is a library for composing asynchronous and event-based programs by using observable sequences.
>  It extends the observer pattern to support sequences of data and/or events
>  and adds operators that allow you to compose sequences together declaratively
>  while abstracting away concerns about things like low-level threading, synchronization, thread-safety, concurrent data structures, and non-blocking I/O.
>  > - ReactiveX는 관찰가능한 절차를 통해 비동기, 이벤트 기반 프로그램을 구성하기 위한 라이브러리이다.
>  > - Observer Pattern을 확장하며, Sequence를 조합할 수 있는 연산자를 지원한다.
>  > - low-level Thread, 동기화, Thread 안전성, non-blocking I/O에 관한 우려를 줄인다.

RxJava는 함수형 프로그래밍 방식으로, 그 구성의 핵심 요소는 **Observable**과  **Operator**.
<pre><code>
import io.reactivex.rxjava3.core.Observable;
public class RxExample {
    public static void main(String[] args) {
        Observable.just(1, 2, 3)
                .map(x -> x*10)
                .subscribe(System.out::println);
  }
}
</code></pre>
> - Observable : ReactiveX의 핵심 요소이자 데이터 흐름에 맞게 Consumer에게 알림을 보내는 Class이다.
> - just() : 가장 간단한 Observable 생성 방식이다. (생성 연산자라고도 한다)
> - map() : RxJava의 연산자이다. 데이터를 원하는 형태로 바꿀 수 있다.
> - subscribe() : Observable은 구독(subscribe)을 해야 데이터가 발행된다. 따라서 Observable을 구독하여 데이터를 발행 후, 수신한 데이터를 원하는 방식으로 사용(System.out::println)한다.

![image](https://user-images.githubusercontent.com/49303504/152710678-d80c289a-38d7-415c-a030-15ea3c4662e0.png)
> - 1, 2, 3이 연산자 map을 거쳐 10, 20, 30이 되었다.

## Observable

> RxJava의 핵심 요소인 **Observable**.
![image](https://user-images.githubusercontent.com/49303504/152710786-940a6f25-e628-4523-a210-8ff11aabf2f1.png)
> **Observable**이 데이터 스트림을 처리하교, 완료하면 데이터를 발행(emit)한다.
> 데이터를 발행할 때마다 구독하고 있는 Observer가 알림을 받는다.
> Observer는 수신한 데이터를 가지고 어떠한 일을 한다.

### Subscribe??
> **Observable**이 데이터를 발행(emit)하고 알림(event)를 보내면,
> **Observable**을 구독(subscribe)해 데이터를 소비(consume)한다.
<pre><code>
// Emitter를 통해 알림을 보낸다고 생각하면 된다
public interface Emitter<@NonNull T> {
    void onNext(@NonNull T value);
    void onError(@NonNull Throwable error);
    void onComplete();
}
</code></pre>
> - onNext : 데이터의 발행을 알림
> - onComplete : 모든 데이터의 발행이 완료되었음을 알림, 딱 한 번만 발생하며 이후에 onNext가 발생하면 안됨
> - onError : 오류가 발생했음을 알림, 이후에 onNext와 onComplete가 발생하지 않음

### 예시로 이해하기.
> A와 B가 있다.
>
> A는 B가 뭘 하는지 모르지만 B가 소리를 치면 들을 수 있다.
>
> B는 아프다면 소리 지른다.
>
> A는 B가 소리를 치는 순간 춤을 춘다.
>
> --------------------------------
>
> 여기서 A는 Observer, B는 Observable.
>
> 여기서 A가 소리를 들을 수 있다가 Subscribe.
>
> 춤을 춘다는 do something
>
> B가 소리를 지르는건 emit (onNext)
>
> B가 아프다면은 B 내부 사정.



##### 출처: 
> [1](https://4z7l.github.io/2020/12/01/rxjava-1.html)
> [2](https://4z7l.github.io/2020/12/01/rxjava-2.html)
> [3](https://reactivex.io/intro.html)
