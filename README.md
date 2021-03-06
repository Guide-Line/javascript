## JavaScript Style Guide

- [ktec_responsive_guide](https://github.com/Guide-Line/ktec_responsive_guide)


<a name="top"></a>
### Table of Contents

  1. [Naming](#Naming)
  1. [Types](#Types)
  1. [Comment](#Comment)
  1. [Jquery](#Jquery)
  1. [Array](#Array)
  1. [Function](#Function)
  1. [Variables](#Variables)
  1. [Hoisting ](#Hoisting )
  1. [Commas](#Commas)
  1. [Script in html](#Scriptinhtml)
  
  
  
  
  
  
  
  
  
  
  
  
  
  
---------------------------------------------------------------------------------------------------------------------------------------------
<a name="Naming"></a>
- Naming  

[카멜케이스](https://ko.wikipedia.org/wiki/%EB%82%99%ED%83%80_%EB%8C%80%EB%AC%B8%EC%9E%90) 표기방법으로 진행한다

```js
    ClassNamesLikeThis
    methodNamesLikeThis
    variableNamesLikeThis
    parameterNamesLikeThis
    propertyNamesLikeThis
    
    예)    
    var thisNum = 7;
    
    function privateClass(){
        ...
    }
    
```

<a href="#top">▲ back to top</a>  

---------------------------------------------------------------------------------------------------------------------------------------------
<a name="Types"></a>
- Types
    - [string](https://www.w3schools.com/js/js_strings.asp)
    - [number](https://www.w3schools.com/js/js_numbers.asp)
    - [boolean](https://www.w3schools.com/js/js_booleans.asp)
    - [null](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null)
    - [undefined](https://www.w3schools.com/jsref/jsref_undefined.asp)
    
원시 타입으로 값을 직접 조작할수있다.
    
```js
    //string
    var name = "john doe";
    console.log(name); // => john doe

    //number
    var foo = 1;
    var bar = foo;
    bar = 9;    
    console.log(foo, bar); // => 1, 9
    
     //boolean
    if (true) {
      var x = 5;
    }
    console.log(x); // 5
    
    //null
    var n = null;
    console.log(n * 32); // 콘솔에 0 으로 로그가 남음.   
    
    //undefined
    var x;
    console.log(x); // x 에 값이 정의되지 않았으므로  undefined 가 출력된다
    
    
```

<a href="#top">▲ back to top</a>

---------------------------------------------------------------------------------------------------------------------------------------------
<a name="Comment"></a>
- Comment

아래 와 같이 사용한다

```js
    // 한 줄 주석

    /* 이건 더 긴,
       여러 줄 주석입니다.
     */

    /* 그러나, /* 중첩된 주석은 쓸 수 없습니다 */ SyntaxError */
    
```

함수의 주석을 아래처럼 활용할수 있다.

```js
    /**
    *
    * @param value1 : 내용
    * @param value2 : 내용
    *
    */
    function markDownMake(value1 , value2){
        ...    
    }

```


<a href="#top">▲ back to top</a>

---------------------------------------------------------------------------------------------------------------------------------------------
<a name="Jquery"></a>
- Jquery

jQuery오브젝트의 변수는 선두에 $ 를 부여

```js
    // bad
    var sidebar = $('.sidebar');

    // good
    var $sidebar = $('.sidebar');

    // good
    var $sidebarBtn = $('.sidebar-btn');

```
중복되는 jQuery의 검색결과는 캐쉬화 하여 작성

```js
    
    // bad
    function setSidebar() {
      $('.sidebar').hide();

      // ...stuff...

      $('.sidebar').css({
        'background-color': 'pink'
      });
    }

    // good
    function setSidebar() {
      var $sidebar = $('.sidebar');
      $sidebar.hide();

      // ...stuff...

      $sidebar.css({
        'background-color': 'pink'
      });
    }
    
```

<a href="#top">▲ back to top</a>

---------------------------------------------------------------------------------------------------------------------------------------------
<a name="Array"></a>
- Array

배열 구문을 만들때 [리터럴](https://ko.wikipedia.org/wiki/%EB%A6%AC%ED%84%B0%EB%9F%B4) 구문을 사용

```js
    // bad
    var items = new Array();

    // good
    var items = [];

```

배열 에 값 저장([예제 더보기](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Indexed_collections#Array_object))

```js
    var emp = [];
    emp[0] = "Casey Jones";
    emp[1] = "Phil Lesh";
    emp[2] = "August West"; 

```


<a href="#top">▲ back to top</a>

---------------------------------------------------------------------------------------------------------------------------------------------
<a name="Function"></a>
- Function

함수식

```js
    // 익명함수식
    var anonymous = function() {
      return true;
    };

    // 명시된 함수식
    var named = function named() {
      return true;
    };

    // 즉시실행 함수식
    (function() {
      console.log('hello.');
    })();

```

매개변수(parameter)에 arguments 를 지정하지마세요! 모든 함수는 arguments 가 있습니다. 이는 배열처럼 접근이 가능하기도 합니다.

```js    
    // bad
    function nope(name, options, arguments) {
      // ...stuff...
    }

    // good
    function yup(name, options, args) {
      // ...stuff...
    }
    
```

<a href="#top">▲ back to top</a>

---------------------------------------------------------------------------------------------------------------------------------------------
<a name="Variables"></a>
- Variables

변수를 선언할때 항상 var 를 사용하세요. 그렇지 않으면 전역 변수로 선언 될 수 있습니다.

```js
    // bad
    superPower = new SuperPower();

    // good
    var superPower = new SuperPower();

```

여러 변수를 선언하려면 하나의 var 를 사용하여 변수마다 줄바꿈하여 선언합니다.

```js    
    // bad
    var items = getItems();
    var goSportsTeam = true;
    var dragonball = 'z';

    // good
    var items = getItems(),
        goSportsTeam = true,
        dragonball = 'z';

```

여러개의 변수를 선언시 정의되지 않은 변수를 마지막으로 선언하십시오

```js    
    // bad
    var i, items = getItems(),
        dragonball,
        goSportsTeam = true,
        len;

    // good
    var items = getItems(),
        goSportsTeam = true,
        dragonball,
        length,
        i;

```

<a href="#top">▲ back to top</a>

---------------------------------------------------------------------------------------------------------------------------------------------
<a name="Hoisting"></a>
- Hoisting

자바스크립트에서는 var 선언문 전에 변수를 사용해도 이미 선언된 것으로 간주한다.

```js
    //1
    alert(typeof fn1); // undefined
    alert(typeof value1); // undefined

    var fn1 = function(){ ; };
    var value1 = 'value1';
    
    //2
    alert(typeof fn1); // function
    alert(typeof value1); // string

    1. 자바스크립트는 실행시 모든 변수가 선언 됩니다. 즉, 결과 에서 처럼 변수를 정의 하기전 
    결과는 모두 "undefined"를 반환 합니다.

    2. 하지만 정의된 후의 결과는 각각 function 과 string을 반환 합니다.
    
```

함수 선언문으로 선언된 변수는 호이스팅 동작에서 정의된 값이 위로 끌어 올려집니다.

```js    
    alert(typeof fn1); // function

    function fn1(){ ; };

    alert(typeof fn1); // function
    
    함수 선언문 방식으로 작성한 전역 fn1()
    함수 객체는 var선언문 이전의 결과 에서도 function() 을 반환 합니다.

```

<a href="#top">▲ back to top</a>

---------------------------------------------------------------------------------------------------------------------------------------------
<a name="Commas"></a>
- Commas

선두의 comma는 하지마십시오.

```js
    // bad
    var once
      , upon
      , aTime;

    // good
    var once,
        upon,
        aTime;

    // bad
    var hero = {
        firstName: 'Bob'
      , lastName: 'Parr'
      , heroName: 'Mr. Incredible'
      , superPower: 'strength'
    };

    // good
    var hero = {
      firstName: 'Bob',
      lastName: 'Parr',
      heroName: 'Mr. Incredible',
      superPower: 'strength'
    };

```

말미의 불필요한 쉼표도 하지마세요, IE에서 문제를 일으킬수있습니다.

```js
   // bad
    var hero = {
      firstName: 'Kevin',
      lastName: 'Flynn',
    };

    var heroes = [
      'Batman',
      'Superman',
    ];

    // good
    var hero = {
      firstName: 'Kevin',
      lastName: 'Flynn'
    };

    var heroes = [
      'Batman',
      'Superman'
    ]; 

```

<a href="#top">▲ back to top</a>

---------------------------------------------------------------------------------------------------------------------------------------------
<a name="Scriptinhtml"></a>
- Script in html

웹 브라우저는 HTML 코드와 자바스크립트 코드를 동시에 해석하지 않고 작성된 순서대로([인터프리터](https://namu.wiki/w/%EC%9D%B8%ED%84%B0%ED%94%84%EB%A6%AC%ED%84%B0)) 해석하기 때문에 자바스크립트 코드를 나중에 해석하도록 하면 HTML 문서를 화면에 표시하는 속도가 빨라집니다.

```js
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>Document</title>

        <!-- css 선언 -->
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.5.2/animate.min.css">
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/hover.css/2.1.1/css/hover-min.css">




    </head>
    <body>

        ...



        <!-- script 선언 -->
        <script src="js/main.js"></script>
        <script>
            ...

        </script>
    </body>
    </html>

```

<a href="#top">▲ back to top</a>



