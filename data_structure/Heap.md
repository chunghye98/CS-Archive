# Heap이란?
> 힙과 우선순위 큐에 대해 알아보자.

## 힙 Heap
완전 이진 트리 기반의 자료구조이며, 최소힙과 최대힙 두 가지가 있고 해당 힙에 따라 특정한 특징을 지킨 트리를 의미한다.    
우선순위 큐를 위해 만들어진 자료구조이며, 반 정렬된 상태룰 가진다.

### 시간복잡도
- 삽입 : O(logN)
- 삭제 : O(logN)
- 최대값 또는 최소값 찾기 : O(1)

### 종류
1. 최대 힙(max heap)    
루트 노드에 있는 키는 모든 자식에 있는 키 중에서 가장 커야 한다.
2. 최소 힙(min heap)    
루트 노드에 있는 키는 모든 자식에 있는 키 중에서 최솟값이어야 한다.

### 연산
1. 최대힙의 삽입    
   1. 힙에 새로운 요소가 들어오면, 일단 새로운 노드를 힙의 마지막 노드에 이어서 삽입한다.
   2. 이 새로운 노드를 부모 노드들과의 크기를 비교하며 교환해서 힙의 성질을 만족시킨다. 
2. 최대힙의 삭제
   1. 루트 노드를 삭제한다.
   2. 삭제된 루트 노드에 마지막 노드를 가져온다.
   3. 스왑 과정을 거치며 힙을 재구성한다. 

## 우선순위 큐 Priority Queue
대기열에서 우선순위가 높은 요소가 우선순위보다 낮은 요소보다 먼저 제공되는 자료구조이다. 힙을 기반으로 구현된다.    
Java에서는 PriorityQueue 클래스로 생성한다.

```java
import java.util.PriorityQueue;

public class Example {
	public static void main(String[] args) {
		// 정수의 우선순위 큐를 생성합니다. 낮은 숫자가 높은 우선순위를 갖습니다.
		PriorityQueue<Integer> pq = new PriorityQueue<>();
	}
}
```

커스텀 객체를 사용할 때는 해당 객체가 `Comparable` 인터페이스를 구현하거나, 우선수누이 큐 생성 시 `Comparator`를 제공해야 한다.
```java
import java.util.PriorityQueue;
import java.util.Comparator;

class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

public class Example {
	public static void main(String[] args) {
		// 나이에 따른 우선순위를 가지는 우선순위 큐를 생성합니다.
		PriorityQueue<Person> personQueue = new PriorityQueue<>(new Comparator<Person>() {
			@Override
			public int compare(Person p1, Person p2) {
				return Integer.compare(p1.age, p2.age); // 나이가 낮은 사람이 높은 우선순위를 갖습니다.
			}
		});
	}
}
```



## 참고
면접을 위한 CS 전공지식 노트    
[Heap](https://github.com/gyoogle/tech-interview-for-developer/blob/master/Computer%20Science/Data%20Structure/Heap.md)
