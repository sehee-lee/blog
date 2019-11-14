---
title: '[JavaScript] Start Jest for testing JavaScript'
date: 2019-11-14 10:19:13
category: 'Development'
---

## What is Jest?

![](./images/jest.png)

C++를 이용하여 개발을 진행하는 개발자는 Gtest에 매우 익숙할 것 입니다. Gtest는 google에서 제공하는 unit test tool인데요, 이와 마찬가지로 JavaScript를 위한 testing tool이 있습니다.
Jest가 그 tool인데요, 이 Jest는 매우 심플하면서도 복잡한 configuration을 할 필요가 없어서 사용하기 매우 좋습니다.
그래서 Node.js, React, Angular, Vue.js 등에서 테스트 용으로 주로 사용하고, 최근에 주목받고 있는 [GraphQL](../graphql-what-is-graphql)에서도 사용이 가능합니다.

## Usage Jest
### Install Jest and set package configuration.
먼저 jest를 설치해줘야 합니다. <strong>npm</strong>을 이용하여 설치하면 됩니다. project directory로 이동하여 개발 의존성으로 설치하면됩니다.

~~~bash
npm install --save-dev jest
~~~

install이 끝났으면, 여러분의 javascript project directory로 이동합니다. 이 포스팅에서는 설명을 위해서 "jest-starter" 라는 directory를 생성하여 진행하겠습니다.
초기에 package.json file을 열면 다음과 같이 되어있습니다.

~~~json
{
  "name": "jest-starter",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
~~~

여기서 수정해야 하는 부분은 "scripts"의 "test" 부분입니다. 이 부분은 다음과 같이 수정해줍니다.

~~~json
  "scripts": {
    "test": "jest"
  }
~~~

이는, jest library를 test에 사용하겠다는 의미가 됩니다. 그래서 terminal에 "npm test"를 입력하면 바로 jest가 실행되고 테스트를 할 수 있습니다.
이렇게하면 jest를 사용하기 위한 install과 configuration file 수정이 끝나게 됩니다.

## Create test script file
jest를 기본적으로 project 최상위 directory에 있는 test.js를 실행하게 됩니다. 그러면, test.js를 한번 생성하고 간단한 테스트 코드를 넣어보겠습니다.
먼저, 두 숫자를 입력받아서 더한 값을 return하는 함수인 sum.js를 작성합니다.

~~~javascript
function sum(a, b) {
  return a + b;
}
module.exports = sum;
~~~

그 위에, test.js에 이 함수를 테스트 하는 코드를 넣어줍니다.

~~~javascript
const sum = require('./sum');

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
module.exports = sum;
~~~

이 file은 test를 하는 file입니다. 간단하게 함수를 정의한다고 생각하면 됩니다. 먼저 테스트 title을 포함하여 선언을 해줘야 합니다.

~~~javascript
test('adds 1 + 2 to equal 3', () => {
...
})
~~~

그 다음에는 실행을 한 뒤에 그 값을 비교해 줍니다.

~~~javascript
  expect(sum(1,2)).toBe(3);
~~~

여기서 toBe는 동일한 값이면 OK! 다르면 fail을 표시할 때 사용합니다. 이렇게 test.js file을 생성한 뒤에, npm을 통해서 test를 진행합니다.

~~~bash
npm test
~~~

그러면 다음과 같은 message가 출력되고, 이를 통해서 test 성공 여부를 확인할 수 있습니다.
~~~
> jest-starter@1.0.0 test /Users/chad/sehee_dev/javascripts/jest-starter
> jest

 PASS  ./test.js
  ✓ adds 1 + 2 to equal 3 (2ms)

Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        0.954s
Ran all test suites.
~~~

test.js에 정의한 test case는 총 1개이고, 그 test case의 이름은 " adds 1 + 2 to equal 3"이며 모두 통과했다는 의미입니다.
이렇게 간단하게 test case를 작성하고 이를 이용하면 unit test를 할 수 있습니다. 또한 수행시간 및 성공 여부도 보기 좋게 출력해주기 때문에 개발에 상당한 도움이 됩니다!!
<br>
이 예제는 간단하게 toBe라는 matcher만 사용했지만, 다양한 matcher가 존재합니다. 이에대한 설명은 [jest expect reference document](https://jestjs.io/docs/en/expect)를 참고하시기 바랍니다.
그리고 이 예제는 [git](https://github.com/sehee-lee/jest-starter)을 참고하시면 됩니다 :)

## Reference
> [jest expect reference document](https://jestjs.io/docs/en/expect)<br>
> [jest wikipedia page](https://en.wikipedia.org/wiki/Jest_(JavaScript_framework))