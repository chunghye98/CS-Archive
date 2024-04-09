# Queue란?
> 큐와 덱에 대해 알아보자.

## 큐 Queue
FIFO(First In First Out, 선입선출) 구조를 가지는 자료구조이다.    
Java에서는 기본적으로 생성할 때 LinkedList 클래스로 구현한다. 이때 타입은 꼭 reference type이어야 한다.

```java
import java.util.Queue;

Queue<T> name = new LinkedList<>();
```

### 시간복잡도
삽입 및 삭제에 O(1), 탐색에 O(n)이 걸린다.

### 함수 종류
1. **push(x)**    
x를 queue의 맨 뒤에 추가한다.    
Java에서는 add와 offer로 요소를 큐에 추가할 수 있다. 다만, 추가할 수 없으면 add는 예외를 던지고, offer는 false를 반환한다.

2. **size()**     
queue 안에 들어있는 데이터의 개수를 반환한다. 

3. **empty()**    
queue 안에 남아있는 데이터가 없다면 true, 있다면 false를 반환한다.
Java에서는 isEmpty가 이 기능을 수행한다.

4. **front()**    
queue의 맨 앞에 있는 값을 반환한다. 해당 데이터를 제거하지 않는다.    
Java에서는 element와 peek로 이 기능을 수행할 수 있다. 다만, 큐가 비어잇으면 element는 예외를 던지고, peek는 null을 반환한다.


5. **pop()**    
queue의 맨 앞에 있는 숫자값을 반환한다. 해당 데이터를 제거한다.    
Java에서는 remove와 poll로 큐의 헤드를 제거하고 반환할 수 있다. 다만, 큐가 비어있으면 remove는 예외를 던지고, poll은 null을 반환한다.

## 덱 Dequeue
<img src="https://contents.codetree.ai/problems/571/images/705c1a87-1d5c-4ca2-89fa-3376e01ac04a.png" width="40%">

스택과 큐의 특성을 합친 자료구조이다. 맨 앞/뒤에서 삽입/삭제가 모두 가능하다.    
Java에서는 기본적으로 생성할 때 ArrayDeque 형태의 선언이 필요하다. 이때 타입은 꼭 reference type이어야 한다.

```java
import java.util.Deque;
import java.util.ArrayDeque;

public class Main {
    public static void main(String[] args) {
        Deque<Integer> dq = new ArrayDeque<>();
    }
}
```

### 함수 종류
1. **addFirst(E)**    
맨 앞에 데이터 E를 추가한다.
2. **addLast(E)**    
맨 뒤에 데이터 E를 추가한다.
3. **pollFirst(E)**    
맨 앞에 있는 데이터를 반환하면서 제거한다.
4. **pollLast(E)**    
맨 뒤에 있는 데이터를 반환하면서 제거한다.
5. **size()**    
현대 덱에 들어있는 데이터의 수를 반환한다.
6. **isEmpty()**    
현대 덱이 비어있다면 true, 아니라면 false를 반환한다.
7. **peekFirst()**    
맨 앞에 있는 데이터를 반환한다.
8. **peekLast()**    
맨 뒤에 있는 데이터를 반환한다.


### 시간복잡도
맨 앞/뒤에서 삽입/삭제 네 메소드의 시간복잡도가 모두 O(1)이다.

## 참고
코드트리