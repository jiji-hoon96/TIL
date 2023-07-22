## NaN (Not-a-Number)

- NaN은 "숫자가 아님"을 의미
- 이 값은 주로 숫자 연산에서 유효하지 않은 결과를 나타낼 때 사용
- 0으로 나누거나 숫자가 아닌 값을 숫자로 변환하려고 할 때 NaN이 반환
- NaN은 숫자가 아니므로, `typeof NaN`은 "number"가 됨

```javascript
const result = 10 / "hello"; // NaN
```

## null

- null은 값이 존재하지 않음을 나타내는 특별한 값
- 변수를 초기화했지만 아직 유효한 값을 가지지 않을 때 사용
- null은 자료형이 object인데, 일부 오래된 JavaScript 버전에서는 `typeof null` 을 실행하면 "object"가 반환되지만 이는 버그로 인해 그렇게 정의되었음

```javascript
let person = null; // 값이 아직 설정되지 않음
```

## undefined

- undefined는 변수가 선언되었지만 초기화되지 않았거나, 객체의 속성에 접근하려고 할 때 해당 속성이 존재하지 않을 때 반환
- 변수에 undefined를 할당할 수 있음.

```javascript
let age;
const person = {
  name: "John",
};
console.log(person.age); // undefined
```

## Null 과 Undefined 의 차이점

- null과 undefined는 값이 없음을 나타내지만, 자료형과 의미 다름
- null은 명시적으로 값이 없음을 나타내는 반면, undefined는 초기화되지 않은 변수나 존재하지 않는 속성에 암시적으로 할당
