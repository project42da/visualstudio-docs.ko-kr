---
title: "index 속성(RegExp)(JavaScript) | Microsoft Docs"
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
  - "index"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Index 속성"
  - "문자열 일치"
ms.assetid: d8be1ef6-1bf2-43cd-b0b5-567a61eabaad
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# index 속성(RegExp)(JavaScript)
검색한 문자열에서 처음으로 일치하는 부분이 시작하는 문자 위치를 반환합니다.  읽기 전용입니다.  
  
## 구문  
  
```  
  
RegExp.index   
```  
  
## 설명  
 이 속성과 연결된 개체는 항상 전역 `RegExp` 개체입니다.  
  
 **index** 속성은 0에서 시작합니다.  **index** 속성의 초기 값은 –1입니다.  이 값은 일치하는 부분을 찾을 때마다 변경됩니다.  
  
## 예제  
 다음 예제에서는 **index** 속성의 사용법을 보여 줍니다.  이 함수는 검색 문자열을 반복하여 적용하고 문자열의 각 단어에 **index**와 `lastIndex` 값을 출력합니다.  
  
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
      document.write (arr);  
      }  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)  
  
## 참고 항목  
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)