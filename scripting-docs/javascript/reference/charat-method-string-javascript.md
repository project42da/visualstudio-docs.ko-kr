---
title: "charAt 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "charAt"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "String 개체, 문자 반환"
  - "charAt 메서드"
  - "문자, 부분 반환"
ms.assetid: 63173e15-17f6-47c5-8f94-98ef1eb04c1a
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# charAt 메서드(String)(JavaScript)
지정한 인덱스에서 문자를 반환합니다.  
  
## 구문  
  
```  
  
strObj. charAt(index)  
```  
  
## 매개 변수  
 `strObj`  
 필수 요소.  임의의 `String` 개체 또는 문자열 리터럴입니다.  
  
 `index`  
 필수 요소.  원하는 문자의 0부터 시작하는 인덱스입니다.  
  
## 설명  
 `charAt` 메서드는 지정한 `index`에 해당하는 문자 값을 반환합니다.  문자열에서 첫 번째 문자의 인덱스는 0이고 두 번째 문자는 1이며 이와 같은 식으로 계속 이어집니다.  유효한 범위를 벗어나는 `index` 값은 빈 문자열을 반환합니다.  
  
## 예제  
 다음 예제에서는 `charAt` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";  
document.write(str.charAt(str.length - 1));  
  
// Output: Z  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [String 개체](../../javascript/reference/string-object-javascript.md)