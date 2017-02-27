---
title: "LocationType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LocationType 열거형"
ms.assetid: d3e1eedc-bfd3-4c91-881b-d69565138d0f
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# LocationType
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호에 포함 된 위치 정보의 종류를 나타냅니다.  
  
## 구문  
  
```cpp#  
enum LocationType {   
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
  
## Elements  
 `LocIsNull`  
 위치 정보를 사용할 수 없습니다.  
  
 `LocIsStatic`  
 위치 고정입니다.  
  
 `LocIsTLS`  
 위치는 스레드 로컬 저장소에 있습니다.  
  
 `LocIsRegRel`  
 레지스터 상대 위치를입니다.  
  
 `LocIsThisRel`  
 위치는 `this`\-상대.  
  
 `LocIsEnregistered`  
 위치에서 등록 됩니다.  
  
 `LocIsBitField`  
 위치는 비트 필드입니다.  
  
 `LocIsSlot`  
 위치를 Microsoft 중간 언어 \(MSIL\) 슬롯입니다.  
  
 `LocIsIlRel`  
 MSIL에 상대적인 위치를입니다.  
  
 `LocInMetaData`  
 위치에 대 한 메타 데이터입니다.  
  
 `LocIsConstant`  
 위치는 상수 값입니다.  
  
 `LocTypeMax`  
 위치 유형에서이 열거형의 수입니다.  
  
## 설명  
 사용할 수 있는 속성은 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 인터페이스 심볼의 위치를 이미지 파일에 따라 다릅니다.  자세한 내용은 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)를 참조하십시오.  
  
 값이 열거형에서를 호출 하 여 반환 되는 [IDiaSymbol::get\_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md) 메서드.  
  
## 요구 사항  
 헤더: cvconst.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get\_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)   
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)