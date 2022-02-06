# Atomic Boolean

### AtomicBoolean은 Boolean 자료형을 갖고 있는 wrapping 클래스입니다. 
### AtomicBoolean 클래서는 멀티쓰레드 환경에서 동시성을 보장합니다.

### 자바에서 동시성 문제를 해결하는데 3가지 방법이 있습니다.

- ‘Volatile’은 Thread1에서 쓰고, Thread2에서 읽는 경우만 동시성을 보장합니다. 두 개의 쓰레드에서 쓴다면 문제가 될 수 있습니다. 
- ‘Synchronized’를 쓰면 안전하게 동시성을 보장할 수 있습니다. 하지만 비용이 가장 큽니다. 
- ‘Atomic’ 클래스는 CAS(compare-and-swap)를 이용하여 동시성을 보장합니다. 여러 쓰레드에서 데이터를 write해도 문제가 없습니다. 

### 즉, AtomicBoolean는 synchronized보다 적은 비용으로 동시성을 보장할 수 있습니다.

### 다음은 사용하는 방법입니다.

- 객체 생성:

![image](https://user-images.githubusercontent.com/49303504/152706685-491c7ea1-cf50-463d-9f7b-f14711cc39b1.png)

- get(), set(), getAndSet():
> 참고로 getAndSet(Boolean)은 현재 value를 리턴하고(get), parameter의 값으로 업데이트합니다.

![image](https://user-images.githubusercontent.com/49303504/152706689-7ba917de-d6e3-4742-9e0a-f0e7d6322e65.png)

![image](https://user-images.githubusercontent.com/49303504/152706693-5a06c9f3-f624-486f-8a80-d993a75a747b.png)


- compareAndSet()
> compareAndSet(expect, update)는
> 현재 값(get)이 예상하는 값(expect)와 동일하다면 update 값으로 변경해주고 true를 리턴하고,
> 현재 값(get)이 예상하는 값(expect)와 동일하지 않다면 변경 없이 update 무시하고 false리턴.

![image](https://user-images.githubusercontent.com/49303504/152706695-2d3ce0db-1fbe-4281-bb7d-f4dc1df517a6.png)

##### (출처: https://codechacha.com/ko/java-atomic-types/)
