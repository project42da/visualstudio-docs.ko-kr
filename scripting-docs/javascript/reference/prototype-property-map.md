---
title: "prototype 속성 (Map) | Microsoft Docs"
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
ms.assetid: c7b429cb-97b7-400e-a214-1b18bddd6b02
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 45601bdff2dfc8047f2499ab07dcdedd66662fc5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-map"></a>prototype 속성(Map)
지도 대 한 프로토타입의에 대 한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
map.prototype  
```  
  
## <a name="remarks"></a>설명  
 `map` 인수는 맵의 이름입니다.  
  
 `prototype` 속성을 사용하여 개체 클래스에 기본 기능 집합을 제공합니다. 인스턴스의 새 개체는 해당 개체에 할당된 프로토타입의 동작을 "상속"합니다.  
  
 예를 들어 집합의 최대 요소 값을 반환하는 `Map` 개체에 메서드를 추가하려면 함수를 선언하고 `Map.prototype`에 추가한 다음 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]