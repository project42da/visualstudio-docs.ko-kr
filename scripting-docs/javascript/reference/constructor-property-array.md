---
title: "constructor 속성 (Array) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b78d517b-cb56-4866-b30f-ef8121a27843
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ca779a2fa2356c1f3e1ca816f16531c0930459a4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="constructor-property-array"></a>constructor 속성(Array)
배열을 만드는 함수를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array.constructor  
```  
  
## <a name="remarks"></a>설명  
 필요한 `array` 이름 배열입니다.  
  
 `constructor` 속성은 프로토타입이 있는 모든 개체의 프로토타입 멤버입니다. 여기에 모든 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 제외한 개체는 `Global` 및 `Math` 개체입니다. `constructor` 속성은 해당 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성자 속성의 사용을 보여 줍니다.  
  
```JavaScript  
var x = new Array();  
  
if (x.constructor == Array)  
    document.write("Object is an Array.");  
else  
    document.write("Object is not an Array.");  
  
// Output:  
// Object is an Array.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]