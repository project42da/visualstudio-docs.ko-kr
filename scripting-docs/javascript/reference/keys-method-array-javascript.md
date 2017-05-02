---
title: "keys 메서드(Array)(JavaScript) | Microsoft Docs"
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
ms.assetid: fc5b6a30-642c-4bd7-ad31-a42667af2f3f
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# keys 메서드(Array)(JavaScript)
배열의 인덱스 값을 반환하는 반복기를 반환합니다.  
  
## 구문  
  
```  
arrayObj.keys();  
```  
  
#### 매개 변수  
 `arrayObj`  
 필수 요소.  Array 개체입니다.  
  
## 설명  
  
## 예제  
 다음 예제에서는 배열의 키 값을 가져오는 방법을 보여 줍니다.  
  
```javascript  
var k = ["a", "b", "c"].keys();  
// k.next().value == 0  
// k.next().value == 1  
// k.next().value == 2   
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]