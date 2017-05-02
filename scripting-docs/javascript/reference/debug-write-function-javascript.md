---
title: "Debug.write 함수(JavaScript) | Microsoft Docs"
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
  - "Write"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "write 메서드[JavaScript]"
ms.assetid: fd1cfbb3-46cb-47cc-896c-a70d457dd413
caps.latest.revision: 22
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 22
---
# Debug.write 함수(JavaScript)
문자열을 스크립트 디버거로 보냅니다.  
  
## 구문  
  
```  
  
Debug.write([str1 [, str2 [, ... [, strN]]]])  
```  
  
## 매개 변수  
 *str1, str2, ... , strN*  
 선택 사항입니다.  스크립트 디버거로 보낼 문자열입니다.  
  
## 설명  
 `Debug.write` 함수는 런타임에 스크립트 디버거의 직접 실행 창으로 문자열을 보냅니다.  스크립트를 디버깅하지 않는 경우 `Debug.write` 함수를 사용해도 효과가 없습니다.  
  
 `Debug.write` 함수는 `Debug.writeln` 함수와 거의 동일합니다.  유일한 차이점은 문자열이 전송된 후 `Debug.writeln` 함수가 줄 바꿈 문자를 보낸다는 것입니다.  
  
## 예제  
 이 예제에서는 `Debug.write` 함수를 사용하여 스크립트 디버거의 직접 실행 창에 변수의 값을 표시합니다.  
  
> [!NOTE]
>  이 예제를 실행하려면 스크립트 디버거를 설치하고 스크립트를 디버그 모드로 실행해야 합니다.  
>   
>  Internet Explorer 8에는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 디버거가 포함됩니다.  이전 버전의 Internet Explorer를 사용 중인 경우 [방법: Internet Explorer에서 스크립트 디버깅 사용 및 시작](http://go.microsoft.com/fwlink/?LinkId=133801)을 참조하세요.  
  
```javascript  
var counter = 42;  
Debug.write("The value of counter is " + counter);  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Debug 개체](../../javascript/reference/debug-object-javascript.md)  
  
## 참고 항목  
 [Debug.writeln 함수](../../javascript/reference/debug-writeln-function-javascript.md)