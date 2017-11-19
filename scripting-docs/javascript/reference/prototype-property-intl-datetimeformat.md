---
title: "prototype 속성 (Intl.DateTimeFormat) | Microsoft Docs"
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
ms.assetid: e1e693ff-1775-407e-b655-18a60d238ded
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 64dff17e4aaf62940f4c9c5f8b422fcbceb7212a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-intldatetimeformat"></a>prototype 속성(Intl.DateTimeFormat)
포맷터에 대 한 프로토타입의에 대 한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
dateTimeFormat.prototype  
```  
  
## <a name="remarks"></a>설명  
 `dateTimeFormat` 인수는 포맷터의 이름입니다.  
  
 `prototype` 속성을 사용하여 개체 클래스에 기본 기능 집합을 제공합니다. 인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  
  
 예를 들어 집합의 최대 요소 값을 반환하는 `Intl.DateTimeFormat` 개체에 메서드를 추가하려면 함수를 선언하고 `Intl.DateTimeFormat.prototype`에 추가한 다음 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]