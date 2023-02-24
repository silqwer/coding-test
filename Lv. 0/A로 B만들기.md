### **문제 설명**

문자열 `before`와 `after`가 매개변수로 주어질 때, `before`의 순서를 바꾸어 `after`를 만들 수 있으면 1을, 만들 수 없으면 0을 return 하도록 solution 함수를 완성해보세요.

---

### 제한사항

- 0 < `before`의 길이 == `after`의 길이 < 1,000
- `before`와 `after`는 모두 소문자로 이루어져 있습니다.

---

### 입출력 예

| before | after | result |
| --- | --- | --- |
| "olleh" | "hello" | 1 |
| "allpe" | "apple" | 0 |

---

### 입출력 예 설명

입출력 예 #1

- "olleh"의 순서를 바꾸면 "hello"를 만들 수 있습니다.

입출력 예 #2

- "allpe"의 순서를 바꿔도 "apple"을 만들 수 없습니다.

---

### 나의 풀이 

1. 문자열을 받아 배열로 변환

2. 배열을 정열 시키고 문자열로 변환

3. `before`와 `after`를 비교 후 값을 리턴

```javascript
function solution(before, after) {
    const sortString = (str) =>  str.split('').sort().join('');
    const sortBeforeString = sortString(before);
    const sortAfterString = sortString(after);
    
    return sortBeforeString === sortAfterString ? 1 : 0;
}
```