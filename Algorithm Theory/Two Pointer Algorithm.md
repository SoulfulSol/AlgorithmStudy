### Two Pointer Algorithm

---

알고리즘 풀이 테크닉 중 매우 간단한 발상이지만 쉽게 떠올리지는 못하는,

그래서 반드시 기법 자체를 기억하고 있어야만 하는 **투 포인터** 를 정리하고자 한다.



---

#### Two Pointer 란?

말 그대로 2개의 pointer 변수를 선언하고, 2개의 포인터로 복잡한 문제를 쉽게 풀어내는 기법이다.

내 경험상, 완전 탐색으로는 O(N^2) 이상이 소요되는 문제를 O(N)의 효율성으로 풀어내는 것을 요구하는 문제에서 많이 등장한다.



가장 기본적인 유형은 백준의 **2003번 수들의 합2**이다 (https://www.acmicpc.net/problem/2003).

Leetcode에서는 다양한 유형이 있는데, **3sum** 문제(https://leetcode.com/problems/3sum/) 나,

**Longest Substring Without Repeating Characters** (https://leetcode.com/problems/longest-substring-without-repeating-characters/) 가 있다.



기본 형태로는, 일단 1차원 배열이 주어진다.

그리고 **연속된 배열의 부분을 떼어내서(subarray) 그 부분의 속성을 물어보는 형태**를 갖는다.

완전탐색으로는 '연속된 부분'을 구한다는 것 자체가 이미 O(N^2)를 이미하는데, for문을 2번 돌려야 하기 때문이다.

가령,

```
list = [1,2,3,4,5,6,7,8,9]
```

배열이 있을 때, 연속된 숫자들의 모든 subarray를 탐색하기 위해서는 

```
1을 시작점으로 : [1], [1,2], [1,2,3], [1,2,3,4] ...
2를 시작점으로 : [2], [2,3], [2,3,4]...
3을 시작점으로 : [3], [3,4], [3,4,5]...
...
```

와 같이 탐색해야 하므로 for문이 총 2개가 필요하다.

그러나 이 탐색은 사실 조금 비효율적이다. 

만약 subarrays의 **부분합**을 물어본다면, [1,2,3,4]를 탐색한 후 다시 [2,3,4]를 탐색할 때, 

우리는 이미 [1,2,3,4]를 탐색했었기 때문에 [1,2,3,4]의 합인 10에서 1만 빼주면 바로 [2,3,4]의 합이 도출될 수 있기 때문이다.

[1,2,3,4]에서 1만 빼주는 것, 즉 **해당 범위의 시작과 끝을 가리키고 있는 포인터 2개의 index만 조정하는 것**이 투 포인터의 핵심이다.



만약 어떤 문제에서 **1차원 배열의 연속된 집합 부분을 떼어내서 해당 부분의 속성을 물어본다**면, 

지체없이 투 포인터를 떠올리도록 하자.



---

#### 응용 - Prefix Sum

Will be updated.






