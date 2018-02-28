---
title: "함수가 필요 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5002
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f62ade94-9f6f-4832-9b9b-49a06a385bbe
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa2db3e95d4baece288c9f984a7a9cf7a82c9d1d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="function-expected"></a>함수가 필요합니다.
중 하나를 호출 하려고 하거나는 **함수 프로토타입** 되지 않은 개체에 대 한 메서드는 `Function` 개체 또는 하면 함수 호출 컨텍스트의 개체를 사용 합니다. 때문에 다음 코드에서이 오류를 생성 하는 예를 들어 **예제** 는 함수가 아닙니다.  
  
```JavaScript  
var example = new Object();  // Create a new object called "example".  
var x = example();           // Try and call example as if it were a function.  
```  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   호출 **함수 프로토타입** 에 대 한 메서드 `Function` 개체입니다.  
  
-   함수 호출 연산자를 사용 해야 `()` 만 함수를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수 개체](../../javascript/reference/function-object-javascript.md)   
 [prototype 속성(Object)](../../javascript/reference/prototype-property-object-javascript.md)