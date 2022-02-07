# ConcurrentLinkedQueue


Java의 queue class는 multi-thread 환경에서 critical section에 대한 동기화가 적용되어 있지 않아서,

queue.poll(), 즉 queue 객체 맨 앞에 들어있는 data를 꺼내오는 동작을 수행하며 해당 data를 queue에서 삭제하는 것으로,

또 다시 queue.poll()를 수행하면 다음 data를 꺼내와야 하는데,

multithread 환경에서는 이게 되지 않는다.

### 그래서 ConcurrentLinkedQueue는 thread-safe한 FIFO 자료구조.

LinkedList와 같이 Node라는 내부 class를 기반으로 동작.

- 사용 예시:

<pre>
<code>
import java.util.Queue;
import java.util.concurrent.ConcurrentLinkedQueue;
Queue<YourObject> queue = new ConcurrentLinkedQueue<YourObject>();

//data를 offer 할 때
put: queue.offer(Data);

//data를 꺼낼 때
get: queue.poll();
</code>
</pre>

### BlockingQueue vs ConcurrentLinkedQueue

- ConcurrentLinkedQueue
> non-blocking lock-free queues.
> > 큐의 사이즈를 지정할 수 없을 뿐만 아니라 size 메서드는 상수 시간에 호출되지 않아서 큐에 들어있는 원소의 개수를 파악하는 것이 어려움.
> > > 생산자-소비자(producer-consumer) 모델에서 소비자가 많고 생산자가 하나인 경우에 사용하면 좋다. (내 프로젝트 같은 케이스)

- BlockingQueue
> BLocking & Lock Queue.
> > 생성자의 parameter에 큐의 용량 capacity를 명시하여 size를 지정할 수 있음.
> > > 생산자가 많고 하나의 소비자일 경우에 사용하면 좋다.

##### 출처: 
> [1](https://sup2is.github.io/2019/09/10/concurrent-linked-queue.html)
> [2](https://jjaesang.github.io/java/2019/07/22/java-blockingqueue-vs-concurrentLinkedQueue.html)
> [3]( )
> [4]( )
> [5]( )
