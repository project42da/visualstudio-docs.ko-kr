---
title: "constructor 속성 (Set) | Microsoft Docs"
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
ms.assetid: f350b7eb-8994-40bf-9011-f8b20fcef34f
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea9af6d60c2ae8bc8a383c4cebbf0955e183895e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="constructor-property-set"></a>constructor 속성(Set)
집합을 만드는 함수를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
set.constructor  
```  
  
## <a name="remarks"></a>설명  
 필수 `set`은 집합의 이름입니다.  
  
 `constructor` 속성은 프로토타입이 있는 모든 개체의 프로토타입 멤버입니다. 여기에는 `Global` 및 `Math` 개체를 제외한 모든 내장 JavaScript 개체가 포함되어 있습니다. `constructor` 속성은 해당 특정 개체의 인스턴스를 구성하는 함수에 대한 참조를 포함합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]