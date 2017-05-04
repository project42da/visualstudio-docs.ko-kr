---
title: "compile 메서드(Regular Expression)(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "compile"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Compile 메서드"
  - "소스 코드 컴파일, 정규식"
  - "정규식, 컴파일"
ms.assetid: dc28cae3-478d-49b5-b5ea-203e5edfe195
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# compile 메서드(Regular Expression)(JavaScript)
빠른 실행을 위해 정규식을 내부 형식으로 컴파일합니다.  
  
## 구문  
  
```  
  
rgExp.compile(pattern, [flags])   
```  
  
## 매개 변수  
 `rgExp`  
 필수 요소.  **Regular Expression** 개체의 인스턴스입니다.  변수 이름이나 리터럴일 수 있습니다.  
  
 *pattern*  
 필수 요소.  컴파일할 정규식 패턴을 포함하는 문자열 식입니다.  
  
 `flags`  
 선택 사항입니다.  함께 사용할 수 있는 플래그는 다음과 같습니다.  
  
-   g\(발생할 모든 *패턴*에 대한 전역 검색\)  
  
-   i\(대\/소문자 구분 안 함\)  
  
-   m\(여러 행 검색\)  
  
## 설명  
 **compile** 메서드는 보다 빠른 실행을 위해 *pattern*을 내부 형식으로 변환합니다.  예를 들어 이렇게 하면 루프의 정규식을 더 효율적으로 사용할 수 있습니다.  컴파일된 정규식은 같은 식을 반복적으로 다시 사용할 때 속도가 빨라집니다.  그렇지만 정규식이 바뀌면 이러한 이점이 없어집니다.  
  
## 예제  
 다음 예제에서는 **compile** 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function CompileDemo(){  
   var rs;  
   var s = "AaBbCcDdEeFfGgHhIiJjKkLlMmNnOoPp"  
   // Create regular expression for uppercase only.  
   var r = new RegExp("[A-Z]", "g");  
   var a1 = s.match(r)              // Find matches.  
   // Compile the regular expression for lowercase only.  
   r.compile("[a-z]", "g");  
// Find matches.  
   var a2 = s.match(r)                
   return(a1 + "\n" + a2);  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## 참고 항목  
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)