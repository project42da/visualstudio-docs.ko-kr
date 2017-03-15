---
title: "주석 | Microsoft Docs"
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
  - "SymTabAnnotation 기호"
  - "주석 기호"
ms.assetid: eb9f759b-98a5-45fc-b085-91f1f2666e72
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# 주석
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

위치 프로그램 코드에 주석을 추가할 수 있는 `SymTagAnnotation` 기호입니다.  
  
## 속성  
 다음 표에서이 기호 형식에 대해 유효한 속성을 보여 줍니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|일부 위치를 오프셋 합니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|위치 섹션 부분입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|`DWORD`|[DataKind 열거형](../../debugger/debug-interface-access/datakind.md) 값 중 하나입니다.|  
|[IDiaSymbol::get\_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|이 주석 해당 모듈 내에서 상대 위치입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagAnnotation` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
|[IDiaSymbol::get\_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|`VARIANT`|상수 데이터의 값입니다.|  
|[IDiaSymbol::get\_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|이 주석은 실행 파일 이미지 내의 위치입니다.|  
  
## 참고 항목  
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)   
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)