# var, let, const

- `var`는 function-scoped이고, `let`과 `const`는 block-scoped이다.

> [javascript var, let, const 차이점]: https://gist.github.com/LeoHeo/7c2a2a6dbcf80becaaa1e61e90091e5d



## function-scoped / block-scoped

- `function-scoped`: 함수 내에서만 유효

```javascript
function counter(){
	for(var i=0; i<10; i++){
		console.log('i', i)
	}
}
console.log('i', i) // ReferenceError: i is not defined
```

- `block-scoped`: 블록{} 내에서만 유효



## 자료형 비교

|        | var  | let  | const |
| :----: | :--: | :--: | :---: |
| 재선언 |  O   |  X   |   X   |
| 재할당 |  O   |  O   |   X   |

- var

```javascript
var a = 'test1' 
var a = 'test2' // 변수 재선언 O
a = 'test3'		// 변수 재할당 O
```

- let

```javascript
let a = 'test1'
let a = 'test2' // 변수 재선언 X
a = 'test3'		// 변수 재할당 O
```

- const

```javascript
const a = 'test1'
const a = 'test2' // 변수 재선언 X
a = 'test3'		  // 변수 재할당 X
// const는 변수 선언과 동시에 값을 할당해야한다
```

