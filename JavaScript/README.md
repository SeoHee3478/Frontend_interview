## 🍒 데이터 타입

### 🍕 데이터 타입의 종류는 어떤 것들이 있나요?
- 자바스크립트(ES6)은 7개의 데이터 타입을 제공합니다. 7개의 데이터 타입은 **원시타입**과 **객체타입**으로 분류할 수 있는데요, <br/> <br/>
- **원시타입**에는 정수와 실수의 구분이 없는 `숫자 타입`, `문자열 타입`, 논리적 참과 거짓을 갖는 `불리언 타입`, var키워드로 선언된 변수에 암묵적으로 할당되는 값인 `undefined 타입`, 값이 없다는 것을 의도적으로 명시할 때 사용하는 값인 `null 타입`, ES6에서 추가된 7번째 타입으로 다른 값과 중복되지 않는 유일무이한 값인 `심벌 타입`이 있습니다.<br/>  <br/>
- **객체타입**에는 객체, 함수, 배열 등으로 이루어져 있습니다. 

### 🍕 심벌 타입은 뭐죠?
- **심벌(Symbol)** 은 ES6에서 추가된 7번쨰 타입으로, 변경 불가능한 원시 타입의 값입니다. 심벌 값은 다른 값과 중복되지 않는 유일무이한 값이어서 주로 이름이 충돌할 위험이 없는 객체 프로퍼티 키를 만들기 위해 사용합니다. 

### 🍕 데이터 타입은 왜 필요할까요?
- 데이터 타입은 크게 3가지 이유 때문에 필요한데요,
- 첫번쨰는, 값을 저장할 때 확보해야하는 메모리 공간의 크기를 결정하기 위해(몇 바이트의 메모리 공간을 사용해야 낭비와 손실 없이 값을 저장할 수 있는지 알아야 하기 때문에)<br/>  <br/>
- 두번째는, 값을 참조할 때 한 번에 읽어 들여야 할 메모리 공간의 크기를 결정하기 위해(예시: score 변수애 숫자 타입의 값 100이 저장되어 있는 경우, 저장되어 있는 값이 숫자 타입이므로 8바이트 단위로 읽어 들이지 않으면 값이 훼손됩니다.)<br/>  <br/>
- 세번쨰는. 메모리에서 읽어 들인 2진수를 어떻게 해석할지 결정하기 위해(예시: 모든 값은 데이터 타입을 가지며, 메모리에 2진수로 저장됩니다. 메모리에 저장된 값 0100 0001을 숫자로 해석하면 65지만 문자열로 해석하면 'A'입니다.)

### 🍕 정적 타이핑이 뭔가요?
- 정적타이핑은 코드를 작성 할 때 **데이터 타입을 직접 명시하는 것**(예: `int a = 15`)을 의미합니다. <br/>  <br/>
- 정적 타입 언어는 변수의 타입을 변경할 수 없으며, 변수에 선언한 타입에 맞는 값만 할당할 수 있습니다. 또한, 컴파일 시점에 타입체크를 수행한다. 타입 체크를 통과하지 못했다면 에러를 발생시키고 프로그램의 실행 자체를 막아 타입의 일관성을 강제함으로써 **더욱 안정적인 코드의 구현**을 통해 런타임에 발생하는 **에러를 줄입니다.** <br/>  <br/>
- 정적 타입의 언어에는 C, C++, Java, 코틀린, 고, 하스켈, 서스트, 스칼라 등이 있습니다.  

### 🍕 동적 타이핑이 뭔가요?
- 동적타이핑은 변수를 지정할 때 해당 변수의 데이터 타입을 직접 명시하지 않는 것을 의미합니다. <br/>  <br/>
- 대표적인 예로, JavaScript가 있는데 JavaScript는 이미 선언한 타입에 어떠한 데이터 타입의 값이라도 자유롭게 할당할수 있습니다. 
- 자바스크립트의 변수는 선언이 아닌 할당에 의해 타입이 결정(타입 추론)이 됩니다. 그리고 재할당에 의해 변수의 타입은 언제든지 동적으로 변할 수 있습니다. <br/>  <br/>
- 대표적인 동적 타입 언어로는 자바스크립트, 파이썬, PHP가 있습니다. <br/>  <br/>

### 🍕 정적 타이핑과 동적 타이핑
- 정적 타이핑, 동적 타이핑 모두 결국에는 타입을 지정해야합니다. 타입을 지정하는 방식에서 누가, 언제 하느냐의 차이가 있는 것입니다. 정적 타이핑은 사용자가 직접 타입을 지정하는 것이고, 동적 타이핑은 직접 하지 않고 사용자가 값을 대입하면 자바스크립트 엔진은 사용자가 대입한 값을 바탕으로 타입을 지정합니다. 그리고, '런타임'에 타입 지정이 실행됩니다. (값을 할당할 때 타입이 정해짐)  <br/>  <br/>

- **그렇다면 어떤 언어를 쓰는게 좋을까?** 동적 타이핑 언어는 타입으로 부터 해방되어서 매우 편하다. 하지만 타입을 자유롭게 조작할 수 없으며, 의도치 않은 타입 변환을 통해 출력값이 예상과 다를 수 있습니다. 이 점은 규모가 큰 프로덕트에서 심각한 오류로 발전할 수 있습니다. 그렇기 때문에 정적 타이핑을 통해 타입에 대한 권한을 갖는 것이 안정성 측면에서는 더 좋은 코딩 방식이 될 수 있습니다. 많은 기업에서는 타입 컨트롤을 통해 더 정교한 비즈니스 로직을 구성하는 것을 원하기 떄문에 강타입 언어를 선호한다고 합니다.(ex. TypeScript)

---
## 🍒 타입변환과 단축 평가

### 🍕 명시적 타입 변환이 뭔가요?
- 개발자가 의도적으로 값의 타입을 변환하는 것을 명시적 타입 변환 또는 타입 캐스팅이라고 합니다.(예시 toString으로 숫자를 문자열로 타입 캐스팅하는 것 등이 있다.)

### 🍕 명시적 타입 변환 함수를 예를 들어볼 수 있나요?
1. ** 문자열이 아닌 값을 문자열 타입으로 변환하는 방법(문자열x->문자열) **
    1. String 생성자 함수를 new 연산자 없이 호출하는 방법
    ```js
    String(1); //"1"
    String(true); //"true"
    ```
    2. Object.prototype.toString 메서드를 사용하는 방법
    ```js
    (1).toString(); //"1"
    (true).toString //"true"
    ```
    3. 문자열 연결 연산자를 이용하는 방법
    ```js
    1+''; //"1"
    true+'';//"true
    ```
2. ** 숫자 타입이 아닌 값을 숫자 타입으로 변환하는 방법(숫자 x->숫자) **
    1. Number생성자 함수를 new 연산자 없이 호출하는 방법
    ```js
    Number('0'); //0
    ```
    2. parseInt, parseFloat 함수를 사용하는 방법(문자열->숫자만 가능)
    ```js
    parseInt('0'); //0
    parseFloat('10.53') //10.53
    ```
    3. +단항 산술 연산자를 이용하는 방법
    ```js
    +'0';//0
    ```
    4. *산술 연산자를 이용하는 방법
    ```js
    '0'*1 //0
    ```
3. ** 불리언 타입이 아닌 것을 불리언 타입으로 변환하는 방법(불리언x->불리언) **
    1. Boolean 생성자 함수를 new 연산자 없이 호출하는 방법
    ```js
    Boolean([]); // true
    Boolean(''); // false
    ```
    2. !부정 논리 연산자를 두번 사용하는 경우
    ```js
   !!NaN;; // false
   !!null // false
    ```

### 🍕 암묵적 타입 변환이 뭔가요?
- 개발자의 의도와 상관 없이 표현식을 평가하는 도중에 자바스크립트 엔진에 의해 암묵적으로 타입이 자동 변환 되는 것을 의미합니다. (자바스크립트는 가급적 에러를 발생시키지 않도록 암묵적 타입 변환을 통해 표현식을 평가한다.)

1. 문자열 타입으로 변환
```js
1+'2' // "12"
```
2. 숫자 타입으로 변환
```js
1-'1'//0
```
3. 불리언 타입으로 변환
```js
if('') console.log(x); //빈 문자열은 false로 평가되어 아무것도 출력되지 않음
```
### 🍕 truthy / falsy 한 값이 뭔가요?
- 자바스크립트 엔진은 불리언 타입이 아닌 값을 참으로 평가되는 값인 Truthy 값 또는 거짓으로 평가되는 값인 Falsy값으로 구분합니다. 즉, 제어문의 조건식과 같이 불리언 값으로 평가되어야 할 문맥에서 Truthy값은 true로, Falsy값은 false로 암묵적으로 타입 변환됩니다.

** falsy한 값**
```js
false
undefined
null
0, -0
NaN
''(빈 문자열)
```
- Falsy 값에 ! 연산자를 붙이면, 모두 Truthy한 값으로 평가되어 실행 가능해집니다.

## 🍒 배열

### 🍕 자바스크립트의 배열은 자료구조의 배열과 같나요?
- 결론적으로 자바스크립트 배열은 배열이 아닙니다. 자료구조에서 말하는 배열은 **동일한 크기의 메모리 공간이 빈틈없이 연속적으로 나열된 자료구조**를 의미합니다. 즉, 배열의 요소는 하나의 데이터 타입으로 통일되어 있으며 서로 연속적으로 인접해 있는데, 이를 밀집 배열이라고 합니다. 하지만, 자바스크립트의 배열은 요소를 위한 **각각의 메모리 공간은 동일한 크기를 가지 않아도 되며, 연속적으로 이어져 있지 않습니다.**(희소 배열) 이처럼 자바스크립트의 배열은 엄밀히 말해 일반적인 의미의 배열이 아니고, **일반적인 배열의 동작을 흉내 낸 특수한 객체**입니다.


### 🍕 배열의 메서드는 어떤 종류가 있나요?
- 배열 메서드는 크게 두 종류로 나눌 수 있습니다. `원본 배열을 직접 변경하는 메서드`와 `새로운 배열을 생성하여 반환하는 메서드`가 있습니다. 예를 들어 push 메서드는 원본 배열에 원소를 추가하여 직접 변경하고, concat메서드는 원본 배열을 직접 변경하지 않고 새로운 배열을 생성하여 반환합니다. ES5부터 도입된 배열 메서드는 대부분 원본 배열을 직접 변경하지 않지만 초창기 배열 메서드는 원본 배열을 직접 변경하는 경우가 많습니다. 원본 배열을 직접 변경하는 메서드는 외부 상태를 직접 변경하는 **부수효과** 가 있으므로 사용할 때 주의해야 합니다. 따라서 가급적 원본 배열을 직접 변경하지 않는 메서드를 사용하는 편이 좋습니다. 

|메서드 명|역할|원본 배열 변경 여부|
|------|---|---|
|`Array.isArray`|Array 생성자 함수의 정적 메서드|❌3|
|`Array.prototype.indexOf`|원본 배열에서 인수로 전달된 요소를 검색하여 인덱스를 반환|❌|
|`Array.prototype.push`|인수로 전달받은 모든 값을 원본 배열의 마지막 요소로 추가하고 변경된 lengh 프로퍼티 값을 반환|⭕|
|`Array.prototype.pop`|원본 배열에서 마지막 요소를 제거하고 제거한 요소를 반환|⭕|
|`Array.prototype.unshift`|인수로 전달받은 모든 값을 원본 배열의 선두에 요소로 추가하고 변경된 length 프로퍼티 값을 반환|⭕|
|`Array.prototype.shift`|원본 배열에서 첫 번째 요소를 제거하고 제거한 요소를 반환|⭕|
|`Array.prototype.concat`|인수로 전달된 값들을 원본 배열의 마지막 요소로 추가한 새로운 배열을 반환|❌|
|`Array.prototype.splice`|원본 배열의 중간에 요소를 추가하거나 중간에 있는 요소를 제거|⭕|
|`Array.prototype.slice`|인수로 전달된 범위의 요소들을 복사하여 배열로 반환|❌|
|`Array.prototype.join`|원본 배열의 모든 요소를 문자열로 변환 후, 인수로 전달받은 구분자로 연결한 문자열을 반환|❌|
|`Array.prototype.reverse`|원본 배열의 순서를 반대로 뒤집음|⭕|
|`Array.prototype.fill`|인수로 전달받은 값을 배열의 처음부터 끝까지 요소로 채운다2|⭕|
|`Array.prototype.includes`|배열 내에 특정 요소가 포함되어 있ㄴ는지 확인하여 true또는 false를 반환|❌|

### 🍕 고차 함수에 대해서 아나요?
- 고차 함수란 함수를 인자로 전달 받거나 함수를 반환하는 함수를 말합니다. 자바스크립트의 함수는 일급 객체 이므로 함수를 인수로 전달할 수 있으며 반환할 수도 있습니다. 고차 함수는 외부 상태의 변경이나 가변 데이터를 피하고 불변성을 지향하는 함수형 프로그래밍에 기반을 두고 있습니다. 
- 이렇게 함수형 프로그래밍을 기반에 두는 고차함수를 통해 부수 효과를 최대한 억제하여 오류를 피하고 프로그램의 안정성을 높일 수 있습니다.


### 🍕 forEach 메서드와 map메서드의 차이점에 대해 알고 있나요?
- forEach와 map 메서드의 고통점은 자신을 호출한 배열의 모든 요소를 순회하면서 인수로 전달받은 콜백 함수를 반복 호출한다는 것 입니다. 하지만 forEach는 언제나 undefined를 반환하고, map 메서드는 콜백함수의 반환값들로 구성된 새로운 배열을 반환한다는 것입니다. forEach는 단순히 반복문을 대체하기 위한 고차함수이고, map은 요소 값을 다른 값으로 매핑한 새로운 배열을 생성하기 위한 고차함수입니다.

------

## 🍒 함수

### 🍕 자바스크립틑에서 함수를 정의하는 방법은 몇가지가 있나요?
- 크게 4가지가 있는데, 첫번째는 함수 이름을 생략할 수 없는 함수 선언문, 두번째는 변수에 할당한 함수 표현식이다. 함수 표현식은 함수 이름을 생략하는 익명함수처럼 쓸 수 있다. 세번째는 Function 생성자 함수로 정의하는 방법이다. JS가 제공하는 빌트인 함수인 Function 생성자 함수에 매개변수 목록, 함수 몸체를 문자열로 전달하면서 new연산자와 함께 호출하면 함수 객체를 생성할 수 있다. 마지막으로 네뻔째는 ES6에서 도입된 화살표함수는 function 키워드 대신 화살표를 사용해 좀 더 간략한 방법으로 함수를 선언할 수 있다. 화살표 함수는 항상 익명함수로 정의한다는 특징이 있다.

### 🍕 함수 선언문과 함수 표현식은 어떤 차이가 있나요?
- `함수 선언문`으로 정의한 함수는 `함수 선언문` 이전에 호출할 수 있으나 `함수 표현식`으로 정의한 함수는 `함수 표현식` 이전에 호출할 수 없다. 이는 `함수 선언문`으로 정의한 함수와 `함수 표현식`으로 정의한 함수의 생성 시점이 다르기 때문이다. 런타임 이전에 JS엔진에 의해 `함수 선언문`이 먼저 실행되어 런타임 이전에 함수 객체가 먼저 생성된다. 따라서 `함수 선언문` 이전에 함수를 참조할 수 있으며 호출할수 있다. ** 이처럼 `함수 선언문`이 코드의 선두로 끌어 올려진 것처럼 동작하는 자바스크립트 고유의 특징을 함수 호이스팅이라고 한다. ** 

### 🍕 즉시 실행 함수에 대해서 알고 있나요? 알고 있다면 아는 내용에 대해서 말해보세요.
1. 함수 정의와 동시에 즉시 호출되는 함수를 즉시 실행함수라고 합니다. 단 한번 호출되며 다시 호출할 수 없습니다.
2. 즉시 실행 함수는 이름이 없는 익명함수를 사용하는 것이 일반적입니다. 함수 이름이 있는 기명 즉시 실행함수도 사용할 수는 있으나 다시 호출할 수는 없습니다.
3. 즉시 실행 함수는 함수 선언문의 형식에 맞지 않기 때문에 반드시 그룹 연산자로 감싸야합니다.

## 🍒 스코프
### 🍕 스코프가 뭔가요?
- 스코프는 식별자가 유효한 범위를 뜻합니다. 모든 식별자는 자신이 선언된 위치에 의해 다른코드가 식별자 자신을 참조할 수 있는 유효범위가 결정됩니다.

### 🍕 스코프는 어떤 종류가 있죠?
- 스코프는 크게 전역 스코프와 지역 스코프로 구분됩니다. 
- 전역은 코드의 가장 바깥 부분을 의미하며 전역에 변수를 선언하면 전역 스코프를 갖는 전역 변수가 되고, 이 전역 변수는 어디서든 참조할 수 있습니다.
- 지역은 함수 몸체 내부를 의미하며 지역에 변수를 선언하면 지역 스코프를 갖는 지역 변수가 되고, 이 지역 변수는 자신의 스코프와 하위 스코프에서 유효합니다.

### 🍕 렉시컬 스코프를 아나요? 안다면 렉시컬 스코프는 무엇을 의미하나요?
- 함수를 어디서 호출 했는지에 따라 함수의 상위 스코프를 정하면 동적 스코프,  어디서 정의 했는지에 따라서 함수의 상위 스코프를 결정하는 것이 정적 스코프, 즉 렉시컬 스코프를 의미합니다.  clojure, perl 등의 몇몇 오래된 언어들이 동적 스코프 방식을 따르고 있고, C++/C, Java, Javascript 등의 언어는 정적 스코프 방식을 따르고 있습니다. 


### 🍕 전역 변수로 변수를 선언하면 생기는 문제점은 무엇이 있을까요?
- 크게 4가지 문제점이 있는데 첫번째는 전역 변수를 사용하면 모든 코드가 변수를 참조하고 변경할 수 있는 암묵적 결합을 허용한다는 것입니다. 변수의 스코프가 클수록 코드의 가독성은 나빠지고 의도치 않게 상태가 변경될 수 있는 위험도 높아집니다.
- 두번쨰는 생명주기가 길어 메모리 리소스도 오랜기간 소비합니다. 또한 변수 이름이 중복되면 의도치 않은 재할당이 이루어집니다.
- 세번째는 전역변수는 스코프 체인 상에서 종점에 존재하여 변수 검색 시 가장 마지막에 검색이 됩니다. 그래서 검색속도가 가장 느리다는 단점이 있습니다.
- 마지막으로 js의 큰 문제점중 하나가 파일이 분리되어 있다고 해도 하나의 전역 스코프를 공유한다는 것입니다. 따라서 다른 파일내에서 동일한 이름으로 명명된 전역 변수나 전역 함수가 같은 스코프 내에 존재할 경우 예상하지 못한 결과를 가져올 수 있습니다.
- 정리하자면 전역변수로 변수를 선언하면 암묵적 결함, 변수의 긴 생명주기, 스코프 체인 상에서 종점에 존재, 네임스페이스 오염의 단점들이 있습니다.
