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

-   소스 파일은 2000줄 내 로 작성

-   public class는 한 파일 당 한 개만 작성

###  소스 파일 구조


1.  Beginning Comments
소스파일은 파일에 대한 주석으로 시작

``` java
/* 
 * Classname
 * 
 * Version info
 */
```

3.  Package and Import Statements
    
4.  Class and Interface Declarations our spaces

---
##  Indentation

-   들여쓰기는 4 spaces로 작성
    
###  Line Length

-   한 줄은 100자 이내로 작성
    

### Wrapping Lines


- ',' 앞에서 나눈다.

- 연산자 뒤에서 나눈다.

- 높은 수준부터 나누는걸 우선으로 한다.

- 새로운 줄은 윗 줄의 같은 수준과 맞춘다

- 위의 규칙을 지켰을 때 가독성을 떨어지면 들여쓰기를 8 spaces로 한다.

- examples

  
  - 나쁜 예시
  
    ```java
    // wrong : breaked before a comma
    function(expression1, expression2, expression3
             , expression4, expression5);
    
    // wrong : breaked after an operator
    result = number1 * (number2 + number3 - number4) +
    	 number5;
    
    //wrong : confusing code
    if (condition1
        && condition2
        || condition4) {
        //statement
    }
    ```
    
  - 좋은 예시
      ```java
      // right
      function(expression1, expression2, expression3,
               expression4, expression5);

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


- 한 줄에 한 변수만 작성


  - 나쁜 예시

    ```java
    int a, b;		// wrong
    ```

  - 좋은 예시

    ```java
    int a;			// right
    int b;
    ```

### Initialization


-   선언할 때 초기화 권장
    
    ```java
    int a = 9;
    Car car = new Car();
    ```

### Placement


-   블록의 맨 처음에 작성
    
    ```java
    public static void main(String[] args) {
        int big = 9;
        Car car = new Car();			//init when declare
        
        //statements
        //statements
        
        if(big == 9) {
            int sum = 0;				//declare at first in block
            int[] values = new int[9]
            
            //statements
            //statements
        }
    }
    ```
    
    
    
    

### Class and Interface Declarations


-   Method 이름이랑 ‘(‘ 사이에 공백 없이 작성
    
-   ‘{‘ 는 declaration statement랑 같은 라인에 작성
    
-   ‘}’는 opening 블록에 맞추어 작성
    
-   빈 블록은 ‘{}’ 으로 작성
    
    ```java
    void calculate(int a, int b) {		    //right
        // statements
    }
    
    void emptyFunction() {}					// right
    
    void calculate (int a, int b) {			// 메소드 이름이랑 괄호는 공백 없이
    	emptyFuncion ();					// 메소드 이름이랑 괄호는 공백 없이
    }
    
    ```
    
    

---
## Statements


1. 각각의 라인에는 한 statement만 작성

   ```java
   // don't do
   a = 90; a++;
   
   //do this
   a = 90;
   a++;
   ```

   

### return Statements


-   return 가급적 마지막에 사용

### if, if-else, if else-if else Statements


-   한 줄만 있어도 '{',  '}' 사용

- else 는 ‘}’ 같은 줄에 한 칸 띄어쓰고 사용

  ```java
  if (isEmpty) {
      System.out.println("empty");
      // statements
  } else {
      System.out.println("not empty");
  }
  ```

  

### for Statements


-   initial, update에는 한 statement만

- 여러 statement일 경우 for문 위에 쓰기

  ```java
  int i;
  char j;
  for (i = 0, j = 'a'; i < N, i++, j++) { 		// run, but don't do
      // statements
  }
  
  
  //do
  int i = 0;
  char j = 'a';
  for (; i < N; i++) {
      // statements
      j++
  }
  //or
  int i = 0;
  char j = 'a';
  while (i <N) {
      // statements
      i++;
      j++;
  }
  ```

  

### while Statements

-   do-while 안 쓰기
    -   안 쓰는 사람이 많고 초보 개발자는 독해하는데 어려움이 있음.

### switch Statement

-   if 3개 이상일 땐 switch

-   break; 을 의도적으로 안쓰는 경우 /* falls through */ 써주기

- default 필수

  ```java
  // don't do
  if (a == 1) {
      // statements
  } else if (a ==6) {
      // statements
  } else if (a == 8) {
      // statements
  } else {
      // statements
  }
  
  // do
  switch (a) {
      case 1:
          // statements
          break;
      case 6:
          // statements
          break;
      case 8:
          // statements
          break;
      default :
          // statements
          break;
  }
  
  // falls through example
  switch (command) {
      case "bye and quit":
          sayBye();
          /* falls through */
      case "just quit":
          quit();
          break;
      default :
          keepDoing();
          break;
  }
  ```

  


### try-catch Statements

-   Exception만 쓰기 금지
    
    ```java
    try {
        function(); // a function that throw FileNotFoundException
    } catch (FileNotFoundException e) {			// don't do "catch (Exception e)"
        System.out.println(e.toString);
    }
    ```
    
    

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


-   모두 소문자 사용
-   com.nuvilabs.***.///
-   *** : test, prototype, null
-   /// : app Name
-   ex) 

    -   com.nuvilabs.prototype.foodscanner
    -   com.nuvilabs.test.ml-kit

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
5.  한 줄에 여러 assign 금지   `a = b = c = 4`
6.  //TODO -> 가짜 코드를 수정해야 하는 경우
7.  //FIXME -> 안돌아가는코드
    

  


---
## 그 외

삼항연산자 자제

continue, break 자제

사용가능 축약어 정하기( AWS 이런거? )

|   축약어    |             뜻              |
| :---------: | :-------------------------: |
| HTTP, HTTPS | HyperText Transfer Protocol |
|    HTML     |                             |
|     AWS     |     Amazon Web Service      |
|     URL     |                             |
|             |                             |

