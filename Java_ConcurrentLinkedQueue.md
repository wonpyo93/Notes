# ConcurrentLinkedQueue

### ConcurrentLinkedQueue는 thread-safe (multi-thread purpose)한 FIFO 자료구조.
### LinkedList와 같이 Node라는 내부 class를 기반으로 동작.

### 자바에서 동시성 문제를 해결하는데 3가지 방법이 있습니다.

- ‘Volatile’은 Thread1에서 쓰고, Thread2에서 읽는 경우만 동시성을 보장합니다. 두 개의 쓰레드에서 쓴다면 문제가 될 수 있습니다. 
- ‘Synchronized’를 쓰면 안전하게 동시성을 보장할 수 있습니다. 하지만 비용이 가장 큽니다. 
- ‘Atomic’ 클래스는 CAS(compare-and-swap)를 이용하여 동시성을 보장합니다. 여러 쓰레드에서 데이터를 write해도 문제가 없습니다. 

### 즉, AtomicBoolean는 synchronized보다 적은 비용으로 동시성을 보장할 수 있습니다.

### BlockingQueue vs ConcurrentLinkedQueue
> ConcurrentLinkedQueue --> non-blocking lock-free queues.
> > 큐의 사이즈를 지정할 수 없을 뿐만 아니라 size 메서드는 상수 시간에 호출되지 않아서 큐에 들어있는 원소의 개수를 파악하는 것이 어려움.
> > > 생산자-소비자(producer-consumer) 모델에서 소비자가 많고 생산자가 하나인 경우에 사용하면 좋다. (내 프로젝트 같은 케이스)
> BlockingQueue --> BLocking & Lock Queue.
> > 생성자의 parameter에 큐의 용량 capacity를 명시하여 size를 지정할 수 있음.
> > > 새앗ㄴ자가 많고 하나의 소비자일 경우에 사용하면 좋다.

##### (출처: https://sup2is.github.io/2019/09/10/concurrent-linked-queue.html, )
