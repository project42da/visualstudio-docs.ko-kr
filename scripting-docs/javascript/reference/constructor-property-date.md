---
title: "constructor 속성 (Date) | Microsoft Docs"
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
ms.assetid: 5db153a1-788b-4a61-bfc8-2d2ec38f36ea
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 798064117e17ee5b2988396de3c6545917373b10
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="constructor-property-date"></a>constructor 속성(Date)
날짜를 만드는 함수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
date.constructor  
```  
  
## <a name="remarks"></a>설명  
 필요한 `date` 날짜 개체의 이름입니다.  
  
 `constructor` 속성은 프로토타입이 있는 모든 개체의 프로토타입 멤버입니다. `constructor` 속성은 해당 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성자 속성의 사용을 보여 줍니다.  
  
```JavaScript  
var x = new Date("Hi");  
  
if (x.constructor == Date)  
    document.write("Object is a date.");  
  
// Output:  
// Object is a date.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]