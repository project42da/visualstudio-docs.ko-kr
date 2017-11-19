---
title: "prototype 속성 (Intl.Collator) | Microsoft Docs"
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
ms.assetid: c1bbb523-fb55-4395-b357-34d91cf5bba0
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 696535afde8c497bc98fc2c81a03854d66add6f4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-intlcollator"></a>prototype 속성(Intl.Collator)
병합 하는 장치에 대 한 프로토타입의에 대 한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
collator.prototype  
```  
  
## <a name="remarks"></a>설명  
 `collator` 인수는 병합기의 이름입니다.  
  
 `prototype` 속성을 사용하여 개체 클래스에 기본 기능 집합을 제공합니다. 인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  
  
 예를 들어 집합의 최대 요소 값을 반환하는 `Intl.Collator` 개체에 메서드를 추가하려면 함수를 선언하고 `Intl.Collator.prototype`에 추가한 다음 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]