## 파이썬 문법 정리

</br>

코딩테스트 하루전 날 읽어보아야 할 파이썬 문법 모음

</br>

</br>



### **알파벳인지 아닌지 검사 isalpha()**

```python
x = 'a'

x.isalpha()   # x가 알파벳이면 true, 아니면 false 리턴
```

</br>

</br>



### **문자열 합치기  join() 함수 **

```python
list = ['a', 'b', 'c']

result = ''.join(list)
print(result) # abc출력



a = ['BlockDMask', 'python', 'join', 'example']
 
# 리스트를 문자열로 합치기
result1 = "_".join(a)
print(result1)        # BlockDMask_python_join_example
 
# 리스트를 문자열로 합치기 \n 도 가능함.
result2 = ".".join(a) 
print(result2)        # BlockDMask.python.join.example

```

기억하면 좋을 함수다. 리스트의 값들을 String으로 합쳐준다.

</br>

</br>



### **리스트 초기화**

```python
# 2차원 리스트를 0으로 초기하는 방법
# n x m 을 0으로 초기화 하는것. 
# 인덱스를 굳이 사용하지 않을 땐 언더바_ 를 이용하기도 한다.
d = [[0] * m for _ in range(n)]


# 2차원 리스트를 사용자로부터 입력 받는법
array =[]
for i in range(n) :
	array.append(list(map(int, input().split())))
 
```

</br>

</br>



### **리스트 값 추가 **

```python
array = []

x=0
array.append(x)

```

</br>

</br>



### **리스트 얕은복사 깊은복사**

```python
import copy

a = [1,2,3]

b = a 
c = copy.deepcopy(a)

a[0] = 2

print(b) # [2,2,3] 출력
print(c) # [1,2,3] 출력
```

깊은 복사는 완전 다른 객체 ( 주소값이 달라짐) 로 만들어준다.

</br>

</br>



### **다중 값으로 정렬하기**

```python
result = sorted(result, key = lambda x : (x[0], x[1], x[2]))
```

0번째인자 그다음 1번째 인자 그다음 2번째 인자 순서대로정렬 

혹시 역정렬 원할시에는 - 붙이면됨.

</br>

</br>



### **스택  생성 , 삭제 **

```python
stack = []

stack.append(5)
stack.append(2)
stack.append(3)
stack.append(7)
stack.pop()
stack.append(1)
stack.append(4)
stack.pop()

print(stack)        # [5,2,3,1] 출력
print(stack[::-1])  # [1,3,2,5] 출력

```

기존에 있는 list를 그대로 사용하면 된다.

</br>

</br>



### **큐 생성 , 삭제 **

```python
from collections import deque
queue = deque()

queue.append(5)
queue.append(2)
queue.append(3)
queue.append(7)
queue.popleft()
queue.append(1)
queue.append(4)
queue.popleft()

print(queue)     # deque([3,7,1,4]) 출력
queue.reverse()  # 역순으로 바꾸기
print(queue)     # deque([4,1,7,3]) 출력

```

큐를 사용해야하는 상황이라면 deque 라이브러리를 이용하자! 기본 리스트 보다 수행시간도 빠르고 효율적이다.

</br>

</br>



### **반올림 round() 함수의 필요성**

```python
a = 0.3 + 0.6
print(a) # 0.8999999999999.. 출력

if a == 0.9:
    print(True)
else:
    print(False)       # False 출력


a = 0.3 + 0.6 
print(round(a, 4)) # 5번째 자리에서 반올림하여 4번째 자리까지 보여줘라!
                   # 0.9 출력

if round(a, 4) == 0.9:
    print(True)
else:
    print(False)       # True 출력

```

a 값이 0.899999... 이 나오는 이유는 컴퓨터는 이진값으로 값을 처리하기 때문에 0.3 + 0.9는 미세한 오차가 생기는 것이다. 컴퓨터는 실수를 정확히 표현하지 못하는 경우가 있다. 

</br>

이러한 결과 때문에, 원하는 결과를 얻지 못할 때, round() 반올림함수를 이용할 수 있다.

</br>

</br>


