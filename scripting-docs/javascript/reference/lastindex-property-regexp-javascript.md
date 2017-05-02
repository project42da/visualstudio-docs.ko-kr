---
title: "lastIndex 속성(RegExp)(JavaScript) | Microsoft Docs"
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
  - "lastIndex"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "lastIndex 속성"
ms.assetid: c8ae2a13-6dff-4cbe-b662-aca3d66c2a7f
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# lastIndex 속성(RegExp)(JavaScript)
검색한 문자열에서 마지막으로 일치하는 부분이 시작하는 문자 위치를 반환합니다.  
  
## 구문  
  
```  
  
RegExp.lastIndex  
```  
  
## 설명  
 이 속성과 연결된 개체는 항상 전역 `RegExp` 개체입니다.  
  
 `lastIndex` 속성은 0에서 시작합니다. 즉, 첫째 문자의 인덱스는 0입니다.  초기값은 –1입니다.  이 값은 일치하는 부분을 찾을 때마다 수정됩니다.  
  
 `lastIndex` 속성은 `RegExp` 개체의 `exec` 및 **test** 메서드와 `String` 개체의 `match`, **replace** 및 **split** 메서드에 의해 수정됩니다.  
  
 `lastIndex` 값에는 다음과 같은 규칙이 적용됩니다.  
  
-   일치하는 부분이 없으면 `lastIndex`는 \-1로 설정됩니다.  
  
-   `lastIndex`가 문자열 길이보다 크고 **test**와 `exec`가 수행되지 않으면 `lastIndex`는 \-1로 설정됩니다.  
  
-   `lastIndex`가 문자열 길이와 같은 경우, 패턴이 빈 문자열과 일치하면 정규식이 일치합니다.  그렇지 않으면 일치하는 부분이 없고 `lastIndex`는\-1로 다시 설정됩니다.  
  
-   그 외의 경우 `lastIndex`는 가장 최근에 일치한 부분의 바로 다음 위치로 설정됩니다.  
  
## 예제  
 다음 예제에서는 `lastIndex` 속성을 사용하는 방법을 보여 줍니다.  이 함수는 검색 문자열을 반복하여 적용하고 문자열의 각 단어에 **index**와 `lastIndex` 값을 출력합니다.  
  
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
      document.write (arr.index + "-" + re.lastIndex + " ");  
      document.write (arr);  
      }  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)  
  
## 참고 항목  
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)