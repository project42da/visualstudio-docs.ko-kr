---
title: "valueOf 메서드(Array) | Microsoft Docs"
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
ms.assetid: b694fe65-1297-4580-8af2-406932c06454
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# valueOf 메서드(Array)
지정한 개체의 원시 값을 반환합니다.  
  
## 구문  
  
```  
  
array.valueOf()  
```  
  
#### 매개 변수  
 이 메서드에 매개 변수가 없습니다.  
  
## 반환 값  
 배열 인스턴스를 반환합니다.  
  
## 설명  
 다음 예제에서 인스턴스화된 배열 개체는 이 메서드의 반환 값과 동일합니다.  
  
```javascript  
var arr = [1, 2, 3, 4];  
var s = arr.valueOf();  
  
if (arr === s)  
document.write("same");  
else  
document.write("different");  
  
// Output:  
// same  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]