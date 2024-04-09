# Red Black Tree란?
> 레드블랙트리에 대해 알아보자.

## 레드블랙트리 Red Black Tree
자가 균형 이진 탐색 트리의 일종으로, 각 노드가 레드 혹은 블랙이라는 색상 속성을 갖는 특징이 있다.

### 레드 블랙 트리의 특성
1. 노드는 레드 혹은 블랙이다.
2. 루트 노드는 블랙이다.
3. 모든 리프 노드(NIL 노드)는 블랙이다.
4. 레드 노드의 자식 노드들은 모두 블랙이다. (즉, 레드 노드는 연속해서 나타나지 않는다.)
5. 루트부터 모든 리프 노드까지의 모든 경로에는 같은 수의 블랙 노드가 존재한다.

삽입이나 삭제 과정에서 이 규칙들이 위반되는 경우, 회전(rotation)과 색상 변경을 통해 트리의 균형을 복원한다.

### 연산
- 검색    
O(logN)의 시간 복잡도를 가진다. 
- 삽입    
새로운 노드가 트리에 추가되면, 레드블랙트리의 규칙을 유지하기 위해 필요한 경우에 한하여 회전과 색상 변경이 수행된다.    
이 과정은 트리의 높이에 비례하는 시간 내에 완료되므로 시간 복잡도는 O(logN)이다.
- 삭제    
삭제된 노드의 자리를 대체하기 위해 선택된 노드가 레드블랙트리의 규칙을 위반하는 경우, 여러가지 경우를 처리하기 위한
회전과 색상 변경을 통해 균형을 복원한다. 이 과정 또한 시간복잡도가 O(logN)이다.

### 응용
Java에서는 TreeMap과 TreeSet 클래스에서 레드 블랙 트리를 사용한다. 각각 Map과 Set 인터페이스를 구현하며, 
객체들을 자연 순서 또는 생성자에 제공된 Comparator에 따라 정렬된 상태로 유지한다.