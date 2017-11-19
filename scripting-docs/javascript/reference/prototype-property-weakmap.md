---
title: "prototype 속성 (WeakMap) | Microsoft Docs"
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
ms.assetid: d28b8a9b-38c9-443d-9586-7cc74784bd99
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5cc1bff0d62f2aeb8d6fb78a0857f287fb34078c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-weakmap"></a>prototype 속성(WeakMap)
프로토타입에 대에 대 한 참조를 반환 합니다.는 `WeakMap` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
weakmap.prototype  
```  
  
## <a name="remarks"></a>설명  
 `weakmap` 인수의 이름인는 `WeakMap` 개체입니다.  
  
 `prototype` 속성을 사용하여 개체 클래스에 기본 기능 집합을 제공합니다. 인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  
  
 예를 들어, 메서드를 추가 하는 `WeakMap` 의 가장 큰 요소의 값을 반환 하는 개체는 `WeakMap`함수를 선언 하도록 `WeakMap.prototype`, 다음 사용 하 여 합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]