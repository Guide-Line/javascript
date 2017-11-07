## JavaScript Style Guide


<a name="top"></a>
### Table of Contents

  1. [Naming](#Naming)
  1. [Types](#Types)
  
  
  
  
  
  
  
  
  
  
  
  
  
  
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
    - string
    - number
    - boolean
    - null
    - undefined
    
원시 타입으로 값을 직접 조작한다
    
```js
    var foo = 1;
    var bar = foo;
    bar = 9;
    
    console.log(foo, bar); // => 1, 9

```
