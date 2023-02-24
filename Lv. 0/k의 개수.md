### **문제 설명**

1부터 13까지의 수에서, 1은 1, 10, 11, 12, 13 이렇게 총 6번 등장합니다. 정수 `i`, `j`, `k`가 매개변수로 주어질 때, `i`부터 `j`까지 `k`가 몇 번 등장하는지 return 하도록 solution 함수를 완성해주세요.

---

### 제한사항

- 1 ≤ `i` < `j` ≤ 100,000
- 0 ≤ `k` ≤ 9

---

### 입출력 예

| i | j | k | result |
| --- | --- | --- | --- |
| 1 | 13 | 1 | 6 |
| 10 | 50 | 5 | 5 |
| 3 | 10 | 2 | 0 |

---

### 입출력 예 설명

입출력 예 #1

- 본문과 동일합니다.

입출력 예 #2

- 10부터 50까지 5는 15, 25, 35, 45, 50 총 5번 등장합니다. 따라서 5를 return 합니다.

입출력 예 #3

- 3부터 10까지 2는 한 번도 등장하지 않으므로 0을 return 합니다.

---

### 나의 풀이

1. 주어진 범위의 숫자를 문자열로 변환

2. 문자열을 `split` 후 숫자로 변환해 배열에 하나씩 저장

3. 배열을 순회하며 `k`와 비교 후 일치하면 카운트

4. 결과 리턴

```javascript
function solution(i, j, k) {
    let answer = 0;
    const arr = [];
    
    for(let number = i; number <= j; ++number) {
        String(number).split('').forEach(str => arr.push(Number(str)));
    }
    
    for(const number of arr) {
        if(number === k){
            answer += 1;
        }
    }
    
    return answer;
}
```


### Sathvik1007의 풀이

```java
class Solution {
    public int solution(int i, int j, int k) {
        int answer = 0;
        for (int t = i; t <= j; t++ ){
            StringBuilder sb = new StringBuilder();
            sb.append(t);

            for (int r = 0; r < sb.length(); r++) {
                if ((sb.charAt(r) - '0') == k) {
                    answer++;
                }
            }
        }
        return answer;
    }
}
```

