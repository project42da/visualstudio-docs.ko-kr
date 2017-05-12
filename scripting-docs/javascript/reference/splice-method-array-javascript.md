---
title: "splice 메서드(Array)(JavaScript) | Microsoft Docs"
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
  - "splice"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "splice 메서드"
ms.assetid: 85fdfb13-e3d9-4c89-b524-3ccee7001c93
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# splice 메서드(Array)(JavaScript)
배열에서 요소를 제거하고, 필요하면 그 자리에 새 요소를 삽입한 다음 삭제된 요소를 반환합니다.  
  
## 구문  
  
```  
  
arrayObj.splice(start, deleteCount, [item1[, item2[, . . . [,itemN]]]])  
```  
  
## 매개 변수  
 `arrayObj`  
 필수 요소.  `Array` 개체입니다.  
  
 `start`  
 필수 요소.  배열에서 요소를 제거할 위치이며 0부터 시작하는 위치입니다.  
  
 `deleteCount`  
 필수 요소.  제거할 요소의 수입니다.  
  
 `item1, item2,. . ., itemN`  
 선택 사항입니다.  삭제된 요소 대신 배열에 삽입할 요소입니다.  
  
## 설명  
 `splice` 메서드는 `start` 위치에서 지정된 수만큼 요소를 제거하고 새 요소를 삽입하여 `arrayObj`를 수정합니다.  삭제된 요소는 새 `Array` 개체로 반환됩니다.  
  
## 예제  
 다음 코드에서는 `splice` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var arr = new Array("4", "11", "2", "10", "3", "1");  
arr.splice(2, 2, "21", "31");  
document.write(arr);  
  
// Output: 4,11,21,31,3,1  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [slice 메서드\(Array\)](../../javascript/reference/slice-method-array-javascript.md)