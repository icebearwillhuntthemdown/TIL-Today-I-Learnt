# Iterators
<br/>

## `for...in` and `for...of`
`for...in`과 `for...of`은 자주 쓰는 반복문이다. 굳이 `for(let i = 0; i < arr.length; i++)` 같은 보일러 플레이트를 쓰지 않고도 배열 전체를 훑는 반복문을 쓸 수 있어 편리하다. 자주 쓰면서도 이 둘을 구분하지 않고 써왔는데, 공식 문서를 읽다가 차이를 알게 됐다.

### 차이점?
- `for...in`: key, 즉 인덱스 중심
- `for...of`: value, 즉 값 중심
<br/>

### 예시
코드로 보면 더 이해하기 쉽다. 아래와 같이 빈 배열 weBareBears에 bears 배열에 있는 곰들의 이름을 넣으려고 한다.
```typescript
let weBareBears = []
const bears = ['Grizz', 'Panda', 'Icebear']
```

`for...in`는 key 중심이라고 했다. 아래의 경우 bear는 bears의 key, 그러니까 인덱스를 가리킨다. 
```typescript
for (let bear in bears) {
    weBareBears.push(bear)  
}
console.log(weBareBears)    // ["0", "1", "2"]
weBareBears.length = 0      // 배열 clear
```

그래서 `for...in`으로 원하는 결과를 내려면 아래와 같이 bear를 key 위치에 두어야 한다.
```typescript
for (let bear in bears) {
    weBareBears.push(bears[bear])
}
console.log(weBareBears)    // ["Grizz", "Panda", "Icebear"] 
weBareBears.length = 0      // 배열 clear
```

이 경우에는 value 중심의 `for...of`를 쓰면 효율적이다. 아래에서 bear는 bears의 값을 가리킨다.
```typescript
for (let bear of bears) {
    weBareBears.push(bear)
}
console.log(weBareBears)    // ["Grizz", "Panda", "Icebear"]
```
<br/><br/>

### `break` & `continue`
`for...in`과 `for...of`에서는 단순 `for`에서처럼 `break`와 `continue` 키워드를 사용할 수 있다.
```typescript
for (let bear of bears) {
    if (bear === 'Panda') continue
    weBareBears.push(bear)
}
console.log(weBareBears)    //["Grizz", "Icebear"] 

for (let bear in bears) {
    if (bear === '1') break
    weBareBears.push(bears[bear])
}
console.log(weBareBears)    // ["Grizz"] 
```
<Br/><br/>

## `array.forEach()`
`for...in`이나 `for...of`보다 `forEach()`를 쓰는 경우가 더 잦다. `forEach()`을 사용할 경우 배열의 key, value 모두를 파라미터로 넘길 수 있지만, `break`와 `continue` 키워드를 사용할 수 없다는 차이점이 있다. 

`return`으로 이들을 대체할 수 있다. 

