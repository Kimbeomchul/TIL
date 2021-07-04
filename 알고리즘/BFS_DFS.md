# DFS / BFS

### DFS / BFS란
-  DFS , BFS란 그래프를 탐색하는 방법중 하나이며 DFS는 깊이우선탐색 , BFS 는 너비우선탐색이라 부른다.

### DFS 
-  DFS는 그래프의 최하위노드까지 내려간뒤, 더이상 내려갈 수 없는 곳에도달하면 옆으로 이동하여 반복한다.
- 모든 노드를 방문하고자 하는 경우에 이 방법을 선택함
- 깊이 우선 탐색(DFS)이 너비 우선 탐색(BFS)보다  간단하다. 
- 검색 속도 자체는 너비 우선 탐색(BFS)에 비해서  느리다.


### BFS
- BFS는 최대한 넓게 이동한 다음, 더 이상 갈 수 없을 때 아래로 이동한다. ( 하단 사진참조 ) 
- 주로 두 노드 사이의 **최단 경로**를 찾고 싶을 때 이 방법을 선택한다.  
- 보통 BFS는 Collection라이브러리의 Deque를 사용한다. 
  
  
### DFS 예시코드
```
def DFS_with_adj_list(graph, root):
    visited = []
    stack = [root]

    while stack:
        n = stack.pop()
        if n not in visited:
            visited.append(n)
            stack += graph[n] - set(visited)
    return visited

print(BFS_with_adj_list(graph_list, root_node))
```

### BFS 예시코드
```
from collections import deque

def BFS_with_adj_list(graph, root):
    visited = []
    queue = deque([root])

    while queue:
        n = queue.popleft()
        if n not in visited:
            visited.append(n)
            queue += graph[n] - set(visited)
    return visited
  
print(BFS_with_adj_list(graph_list, root_node))
```

### 문제 
- [백준 1260](https://www.acmicpc.net/problem/1260)
  + 1260 풀이
```
from collections import deque


def DFS(data, root):
    visited = []
    stack = [root]

    while stack:
        n = stack.pop()
        if n not in visited:
            visited.append(n)
            if n in data:
                temp = list(set(data[n]) - set(visited))
                temp.sort(reverse=True)
                stack += temp
    return ' '.join(str(i) for i in visited)


def BFS(data, root):
    visited = []
    queue = deque([root])

    while queue:
        n = queue.popleft()
        if n not in visited:
            visited.append(n)
            if n in data:
                temp = list(set(data[n]) - set(visited))
                temp.sort()
                queue += temp
    return ' '.join(str(i) for i in visited)

n, m, v = map(int, input().split())
data = {}
for _ in range(m):
    x, y = map(int,input().split())
    if x not in data:
        data[x] = [y]
    elif y not in data[x]:
        data[x].append(y)

    if y not in data:
        data[y] = [x]
    elif x not in data[y]:
        data[y].append(x)

print(DFS(data,v))
print(BFS(data,v))
```


