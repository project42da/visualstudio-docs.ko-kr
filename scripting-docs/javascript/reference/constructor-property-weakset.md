---
title: "constructor 속성 (WeakSet) | Microsoft Docs"
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
ms.assetid: 234e7104-9b78-4bfa-8f77-2bc44a570928
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5519c37f459e8236c6ed482b181799076832c50b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="constructor-property-weakset"></a>constructor 속성(WeakSet)
`WeakSet`을 만드는 함수를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
weakset.constructor  
```  
  
## <a name="remarks"></a>설명  
 필수 `weakset`은 집합의 이름입니다.  
  
 `constructor` 속성은 프로토타입이 있는 모든 개체의 프로토타입 멤버입니다. 여기에는 `Global` 및 `Math` 개체를 제외한 모든 내장 JavaScript 개체가 포함되어 있습니다. `constructor` 속성은 해당 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]