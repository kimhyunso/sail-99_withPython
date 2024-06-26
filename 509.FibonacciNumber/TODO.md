# 문제내용
전에 있던 수와 전전에 있던 수를 더해 현재의 수를 만든다.

$f(a_1-1) + f(a_2-2)$

### 예시
1, 1, 2, 3, 5, 8 ...

![피보나치](https://github.com/kimhyunso/sail-99_withPython/assets/87798982/1494ccb9-518a-41ff-b60c-92c2d0e81dca)
{: .align-center}

# 풀이법
동적계획법과 메모이제이션 기법을 사용하여 풀이를 했다.

1. memo 리스트를 1로 초기화한다.
2. memo의 0번째 인덱스는 0으로 초기화한다. (0, 1, 1, 2) 이런식으로 진행되기 때문
3. 3번째 인덱스 부터 n + 1 인덱스까지 반복문을 돈다 

```python
# n = 3
memo[3] = memo[2] + memo[1]
# n = 4
memo[3] = memo[2] + memo[1]
memo[4] = memo[3] + memo[2]
# n = 5
memo[3] = memo[2] + memo[1]
memo[4] = memo[3] + memo[2]
memo[5] = memo[4] + memo[3]
```
4. 마지막으로 n번째 인덱스의 값을 리턴해준다.


```python
class Solution:
    def fib(self, n: int) -> int:
        memo = [1] * (n + 1)
        memo[0] = 0

        for i in range(3, n + 1):
            memo[i] = memo[i - 1] + memo[i - 2]

        return memo[n] 


# 테스트 케이스
solution = Solution()

print(solution.fib(5))
```






