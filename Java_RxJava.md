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
    public static void main(String[] args){
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

##### 출처: 
> [1](https://4z7l.github.io/2020/12/01/rxjava-1.html)
> [2](https://reactivex.io/intro.html)
