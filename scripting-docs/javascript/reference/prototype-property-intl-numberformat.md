---
title: "prototype 속성 (Intl.NumberFormat) | Microsoft Docs"
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
ms.assetid: 7f6a7e26-108b-4b32-97c2-7f96b9252c50
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b037ce7476574252966e17fcf64246beeaaea1e8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-intlnumberformat"></a>prototype 속성(Intl.NumberFormat)
포맷터에 대 한 프로토타입의에 대 한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
numberFormat.prototype  
```  
  
## <a name="remarks"></a>설명  
 `numberFormat` 인수는 포맷터의 이름입니다.  
  
 `prototype` 속성을 사용하여 개체 클래스에 기본 기능 집합을 제공합니다. 인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  
  
 예를 들어 집합의 최대 요소 값을 반환하는 `Intl.NumberFormat` 개체에 메서드를 추가하려면 함수를 선언하고 `Intl.NumberFormat.prototype`에 추가한 다음 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]