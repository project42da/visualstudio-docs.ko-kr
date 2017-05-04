---
title: "exec 메서드(Regular Expression)(JavaScript) | Microsoft Docs"
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
  - "exec"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Exec 메서드"
  - "문자열 일치"
ms.assetid: 83092452-60cc-4218-b4ae-af9e3cb96c34
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# exec 메서드(Regular Expression)(JavaScript)
정규식 패턴을 사용하여 문자열을 검색하고 그 결과를 배열로 반환합니다.  
  
## 구문  
  
```  
  
rgExp.exec(str)   
```  
  
## 매개 변수  
 `rgExp`  
 필수 요소.  정규식 패턴 및 적용 가능한 플래그를 포함하는 **Regular Expression** 개체의 인스턴스입니다.  
  
 `str`  
 필수 요소.  검색을 수행할 `String` 개체 또는 문자열 리터럴입니다.  
  
## 설명  
 `exec` 메서드가 일치하는 부분을 찾지 못하면 `null`을 반환합니다.  `exec` 메서드가 일치하는 부분을 찾으면 배열을 반환하고, 검색 결과를 반영하도록 전역 `RegExp` 개체의 속성이 업데이트됩니다.  배열의 0 요소는 일치하는 부분 전체를 포함하고 1 – *n* 요소는 각각의 일치하는 부분을 포함합니다.  `match` 메서드를 전역 플래그\(**g**\) 설정 없이 수행하는 것과 같은 결과입니다.  
  
 정규식에 전역 플래그를 설정하면 `exec`는 `lastIndex`값으로 지정된 위치에서 시작하는 문자열을 검색합니다.  전역 플래그를 설정하지 않으면 `exec`는 `lastIndex` 값을 무시하고 문자열의 시작부터 검색합니다.  
  
 `exec` 메서드가 반환하는 배열은 **input**, **index** 및 **lastlndex**의 세 속성을 가집니다. **input** 속성은 전체 검색 문자열을 포함합니다.  **index** 속성은 전체 검색 문자열 내의 일치하는 부분 문자열의 위치를 포함합니다.  `lastIndex` 속성은 일치하는 문자열의 마지막 문자 다음 위치를 포함합니다.  
  
## 예제  
 다음 예제에서는 `exec` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function RegExpTest()  
{  
   var ver = Number(ScriptEngineMajorVersion() + "." + ScriptEngineMinorVersion())  
   if (ver < 5.5)  
   {  
      document.write("You need a newer version of JavaScript for this to work");  
      return;  
   }  
  
   var src = "The quick brown fox jumps over the lazy dog.";  
  
   // Create regular expression pattern with a global flag.  
   var re = /\w+/g;  
  
   // Get the next word, starting at the position of lastindex.  
   var arr;  
   while ((arr = re.exec(src)) != null)  
      {  
      // New line:  
      document.write ("<br />");    
      document.write (arr.index + "-" + arr.lastIndex + " ");  
      document.write (arr[0]);  
      }  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## 참고 항목  
 [match 메서드\(String\)](../../javascript/reference/match-method-string-javascript.md)   
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [search 메서드\(String\)](../../javascript/reference/search-method-string-javascript.md)   
 [test 메서드\(Regular Expression\)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Regular Expression Programming \(JavaScript\)](http://msdn.microsoft.com/ko-kr/3b62e27c-4f07-4726-a95b-6e841807bfaf)