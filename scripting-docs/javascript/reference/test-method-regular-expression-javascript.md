---
title: "test 메서드(Regular Expression)(JavaScript) | Microsoft Docs"
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
  - "test"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "테스트 메서드"
ms.assetid: 4f4b6e39-cb1a-4be9-a66f-7b846075580d
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# test 메서드(Regular Expression)(JavaScript)
검색한 문자열에 패턴이 있는지 여부를 나타내는 부울 값을 반환합니다.  
  
## 구문  
  
```  
  
rgExp.test(str)   
```  
  
## 매개 변수  
 `rgExp`  
 필수 요소.  정규식 패턴 및 적용 가능한 플래그를 포함하는 **Regular Expression** 개체의 인스턴스입니다.  
  
 `str`  
 필수 요소.  검색을 수행할 문자열입니다.  
  
## 설명  
 **test** 메서드는 문자열 안에 패턴이 있는지 확인하여 있으면 **true**를, 없으면 **false**를 반환합니다.  
  
 전역 `RegExp` 개체의 속성은 **test** 메서드로 수정되지 않습니다.  
  
## 예제  
 다음 예제는 **test** 메서드의 사용 예를 보여 줍니다.  이 예제를 사용하려면 함수에 정규식 패턴과 문자열을 전달하세요.  함수는 문자열에 정규식 패턴이 있는지 테스트하고 검색 결과를 나타내는 문자열을 반환합니다.  
  
```javascript  
function TestDemo(re, teststring)  
{  
   // Test string for existence of regular expression.  
   var found = re.test(teststring)  
  
   // Format the output.  
   var s = "";  
   s += "'" + teststring + "'"  
  
   if (found)  
      s += " contains ";  
   else  
      s += " does not contain ";  
  
   s += "'" + re.source + "'"  
   return(s);  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## 참고 항목  
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)