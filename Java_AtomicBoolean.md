# Atomic Boolean

### AtomicBoolean은 Boolean 자료형을 갖고 있는 wrapping 클래스입니다. 
### AtomicBoolean 클래서는 멀티쓰레드 환경에서 동시성을 보장합니다.

![image](https://user-images.githubusercontent.com/49303504/152706481-429b6b20-6f39-4172-8105-7574ee527657.png)

### 자바에서 동시성 문제를 해결하는데 3가지 방법이 있습니다.

> ‘Volatile’은 Thread1에서 쓰고, Thread2에서 읽는 경우만 동시성을 보장합니다. 두 개의 쓰레드에서 쓴다면 문제가 될 수 있습니다.
>	‘Synchronized’를 쓰면 안전하게 동시성을 보장할 수 있습니다. 하지만 비용이 가장 큽니다.
>	‘Atomic’ 클래스는 CAS(compare-and-swap)를 이용하여 동시성을 보장합니다. 여러 쓰레드에서 데이터를 write해도 문제가 없습니다.

### 즉, AtomicBoolean는 synchronized보다 적은 비용으로 동시성을 보장할 수 있습니다.

##### (출처: https://codechacha.com/ko/java-atomic-types/)
