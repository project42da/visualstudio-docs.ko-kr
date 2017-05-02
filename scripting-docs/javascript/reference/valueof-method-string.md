---
title: "valueOf 메서드(String) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: dfb55e6b-e38f-4b49-8196-9693f87126a4
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# valueOf 메서드(String)
문자열을 반환합니다.  
  
## 구문  
  
```  
  
string.valueOf()  
```  
  
#### 매개 변수  
 이 메서드에 매개 변수가 없습니다.  
  
## 반환 값  
 문자열 값을 반환합니다.  
  
## 설명  
 다음 예제에서는 문자열 개체가 반환 값과 같습니다.  
  
```javascript  
var str = "every good boy does fine";  
var strStr = str.valueOf();  
  
if (str === strStr)  
document.write("same");  
else  
document.write("different");  
  
// Output:  
// same  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]