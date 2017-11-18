---
title: LocationType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: LocationType enumeration
ms.assetid: d3e1eedc-bfd3-4c91-881b-d69565138d0f
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5a6a14b3e5e1731c7b9f1fd58181be7adb870d9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="locationtype"></a>LocationType
기호에 포함 된 위치 정보의 종류를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
enum LocationType {   
   LocIsNull,  
   LocIsStatic,  
   LocIsTLS,  
   LocIsRegRel,  
   LocIsThisRel,  
   LocIsEnregistered,  
   LocIsBitField,  
   LocIsSlot,  
   LocIsIlRel,  
   LocInMetaData,  
   LocIsConstant,  
   LocTypeMax  
};  
```  
  
## <a name="elements"></a>요소  
 `LocIsNull`  
 위치 정보를 사용할 수 없는 경우  
  
 `LocIsStatic`  
 위치는 정적입니다.  
  
 `LocIsTLS`  
 스레드 로컬 저장소 위치는입니다.  
  
 `LocIsRegRel`  
 위치는 레지스터 상대입니다.  
  
 `LocIsThisRel`  
 위치는 `this`-상대 합니다.  
  
 `LocIsEnregistered`  
 레지스터에 위치는입니다.  
  
 `LocIsBitField`  
 비트 필드의 위치는입니다.  
  
 `LocIsSlot`  
 위치는 언어 MSIL (Microsoft Intermediate) 슬롯입니다.  
  
 `LocIsIlRel`  
 위치는 MSIL 상대입니다.  
  
 `LocInMetaData`  
 메타 데이터의 위치는입니다.  
  
 `LocIsConstant`  
 위치는 상수 값입니다.  
  
 `LocTypeMax`  
 이 열거형의 위치 유형 수입니다.  
  
## <a name="remarks"></a>설명  
 사용할 수 있는 속성은 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 인터페이스 내에서 이미지 파일에서 기호 위치에 따라 달라 집니다. 자세한 내용은 참조 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)합니다.  
  
 이 열거형의 값에 대 한 호출에서 반환될지는 [idiasymbol:: Get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasymbol:: Get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)   
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)