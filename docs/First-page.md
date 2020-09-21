---
layout: default
title: Java
has_children: false
nav_order: 2
---

# Java Code Convention
{: .no_toc }

<details close markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
---

## 파일 구조   

-   소스 파일은 2000줄 내 로 한다
    
-   public class는 한 파일 당 한 개만 넣는다
    

###  소스 파일 구조


1.  Beginning Comments
소스파일은 파일에 대한 주석으로 시작
``` java
/* 
 * Classname
 * 
 * Version info 
 * 
 * Copyright notice 
 */
```

3.  Package and Import Statements
    
4.  Class and Interface Declarations
our spaces:
``` java
    if (isAwesome){
      return true
    }
```

---
##  Indentation

-   들여쓰기는 4 spaces
    
###  Line Length

-   한 줄은 100자 이내로
    

### Wrapping Lines


- ',' 앞에서 나눈다.

- 연산자 뒤에서 나눈다.

- 높은 수준부터 나누는걸 우선으로 한다.

- 새로운 줄은 윗 줄의 같은 수준과 맞춘다

- 위의 규칙을 지켰을 때 가독성을 떨어지면 들여쓰기를 8 spaces로 한다.

- examples

  ```java
  // right
  function(expression1, expression2, expression3,
           expression4, expression5);
  
  // wrong : breaked before a comma
  function(expression1, expression2, expression3
           , expression4, expression5);
  
  // wrong : breaked after an operator
  result = number1 * (number2 + number3 - number4) +
  	 number5;
  
  // right
  result = number1 * (number2 + number3 - number4)
  	 + number5;
  
  //right : same level -> same indentation
  var = blar1
        * (blar21 + blar22
           / (blar231 % blar232)
           + (blar241 * blar242 + blar243))
        + blar3
        * (blar 41 + blar42)
      
  //wrong : confusing code
  if (condition1
      && condition2
      || condition4) {
      //statement
  }
  
  //right
  if (condition1
      	&& condition2
      	|| condition4) {
      //statement
  }
  
  ```

  

---

## Comment


1.  추가 필요

---

##  Declarations


### Number per Line


-   한 변수는 한 줄에
    
    ```java
    int a, b;		// wrong
    
    int a;			// right
    int b;
    ```

### Initialization


-   선언 되었을 때 초기화 권장
    

### Placement


-   블록의 맨 처음
    

### Class and Interface Declarations


-   Method 이름이랑 ‘(‘ 사이에 공백 없음
    
-   ‘{‘ 는 declaration statement랑 같은 라인
    
-   ‘}’는 opening 블록에 맞춘다
    
-   빈 블록은 ‘{}’ 으로 끝
    

---
## Statements


1.  각각의 라인에는 한 statement만

### return Statements


-   return 가급적 마지막에

### if, if-else, if else-if else Statements


-   한 줄만 있어도 {} 사용

-   else 는 ‘}’ 같은 줄

### for Statements


-   initial, update에는 한 statement만

-   여러 statement일 경우 for문 위에 쓰기

### while Statements

-   do-while 안 쓰기

### switch Statement

-   if 3개 이상일 땐 switch

-   break; 을 의도적으로 안쓰는 경우 /* falls through */ 써주기

-   default 필수


### try-catch Statements

-   Exception만 쓰기 금지
    

---
##  White Space


###  Blank Lines


-   띄우기 잘하기
    
-   추가
    

### Blank Spaces


-   keyword 뒤에 space 하나 (ex: while (true))
    
-   comma 뒤에 space 하나
    
-   모든 operator 양옆으로 space 하나 (‘.’, ‘++,--’ 제외)
    

---
## Naming Conventions


### Packages


-   com.nuvilabs.***.///
    
-   *** : test, prototype, null
    
-   /// : app Name
    

###  Class


-   명사, 대문자로 시작
    
-   축약어 사용 금지 ( URL이나 HTML 보다 유명한거는 가능)
    
-   Upper Camel Case
    

### Interfaces


-   Upper Camel Case
    

###  Methods


-   동사
    
-   Lower Camel Case
    

### variables


-   ‘_’, ‘$’ 금지
    
-   for 문 안에 i, j, k, m, n , characters c, d, e 이것만 한글자 변수명
    

###  Constants


-   ‘_’로 단어 구분
    
-   모두 대문자
    

---
##  Programming Practices


1.  class 나 instance 의 변수는 가급적 private
    
2.  class의 static을 object에서 접근 피하기
    
3.  object의 변수에 직접 접근 피하기
    
4.  코드 안에 상수가 그냥 들어가지 않기
    
5.  한 줄에 여러 assign 금지
    
6.  //TODO -> 가짜 코드를 수정해야 하는 경우
    
7.  //FIXME -> 안돌아가는코드
    

  


---
## 그 외

삼항연산자 자제

continue, break 자제

사용가능 축약어 정하기( AWS 이런거? )
