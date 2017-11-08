## JavaScript Style Guide

- [ktec_responsive_guide](https://github.com/Guide-Line/ktec_responsive_guide)

- [웹퍼블리싱 레퍼런스 바로가기](http://192.168.99.62:777/auction/)

<a name="top"></a>
### Table of Contents

  1. [Naming](#Naming)
  1. [Types](#Types)
  1. [Comment](#Comment)
  1. [Jquery](#Jquery)
  1. [Array](#Array)
  
  
  
  
  
  
  
  
  
  
  
  
  
  
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
    
원시 타입으로 값을 직접 조작한다
    
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

배열 구문을 만들때 [리터럴](http://kssong.tistory.com/26) 구문을 사용

```js
    // bad
    var items = new Array();

    // good
    var items = [];

```

<a href="#top">▲ back to top</a>
