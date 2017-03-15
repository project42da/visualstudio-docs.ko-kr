---
title: "썽크 | Microsoft Docs"
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
  - "썽크 속성[DIA SDK]"
  - "썽크 기호"
ms.assetid: 01abb95f-d89a-465c-a4eb-8e8509598c95
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# 썽크
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

각 `thunk` 로 식별 되는 `SymTagThunk` 태그입니다.  
  
## 속성  
 다음 표에서이 기호 형식에 대해 유효한 속성을 보여 줍니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|액세스 한정자 특성을 가지는 [CV\_access\_e 열거형](../../debugger/debug-interface-access/cv-access-e.md) 값 \(DIA SDK v 8.0에만 이상\).|  
|[IDiaSymbol::get\_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|일부 위치를 오프셋 합니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSegment::get\_addressSection](../../debugger/debug-interface-access/idiasegment-get-addresssection.md)|`DWORD`|위치 섹션 부분입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|부모 클래스에 있는 경우 \(DIA SDK v 8.0에서만 이상\) 바깥쪽.|  
|[IDiaSymbol::get\_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|바깥쪽 클래스 상위 기호 \(DIA SDK v 8.0에만 이상\)의 ID입니다.|  
|[IDiaSymbol::get\_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|썽크 상수 \(DIA SDK v 8.0에만 이상\)으로 표시 되 면 true로 지정 합니다.|  
|[IDiaSymbol::get\_intro](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|`BOOL`|TRUE 이면 썽크 \(DIA SDK v 8.0에만 이상\) 가상 함수에 대 한 소개입니다|  
|[IDiaSymbol::get\_isStatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|DIA SDK v 8.0에만 이상 썽크 정적 간주 되 면 true로 지정 합니다.|  
|[IDiaSymbol::get\_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|썽크는 코드의 바이트 수입니다.|  
|[IDiaSymbol::get\_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|바깥쪽 컴파일, 블록 또는 함수에 대 한 기호입니다.|  
|[IDiaSymbol::get\_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 심볼의 ID입니다.|  
|[IDiaSymbol::get\_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|시작점과 끝점 위치를 고정 있습니다. 자세한 내용은 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md) 열거형입니다.|  
|[IDiaSymbol::get\_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|썽크의 이름입니다.|  
|[IDiaSymbol::get\_pure](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|`BOOL`|TRUE 이면 썽크 순전히 가상 \(DIA SDK v 8.0에만 이상\)입니다.|  
|[IDiaSymbol::get\_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|이 썽크는 모듈 내에서 상대 위치입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagThunk` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
|[IDiaSymbol::get\_targetOffset](../../debugger/debug-interface-access/idiasymbol-get-targetoffset.md)|`DWORD`|일부 썽크 대상의 위치를 오프셋 합니다.|  
|[IDiaSymbol::get\_targetRelativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-targetrelativevirtualaddress.md)|`DWORD`|해당 바깥쪽 블록에 썽크 대상의 상대 가상 주소입니다.|  
|[IDiaSymbol::get\_targetSection](../../debugger/debug-interface-access/idiasymbol-get-targetsection.md)|`DWORD`|썽크 대상의 절 부분입니다.|  
|[IDiaSymbol::get\_targetVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-targetvirtualaddress.md)|`ULONGLONG`|실행 파일 이미지 썽크 대상의 위치입니다.|  
|[IDiaSymbol::get\_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)|`DWORD`|으로 정의 된 형식을 썽크는 [THUNK\_ORDINAL 열거형](../../debugger/debug-interface-access/thunk-ordinal.md).|  
|[IDiaSymbol::get\_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|이 썽크 \(DIA SDK v 8.0에만 이상\) 유형을 지정 합니다.|  
|[IDiaSymbol::get\_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|유형 기호 \(DIA SDK v 8.0에만 이상\)의 ID입니다.|  
|[IDiaSymbol::get\_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`썽크 DIA SDK v 8.0에만 이상으로 맞지 않는 경우|  
|[IDiaSymbol::get\_virtual](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|`BOOL`|`TRUE`썽크 가상 \(DIA SDK v 8.0에만 이상\) 인 경우.|  
|[IDiaSymbol::get\_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|이 썽크 실행 파일 이미지 내의 위치입니다.|  
|[IDiaSymbol::get\_virtualBaseOffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|`DWORD`|이 썽크 DIA SDK v 8.0에만 이상으로 가상 테이블 오프셋입니다.|  
|[IDiaSymbol::get\_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`썽크 \(DIA SDK v 8.0에만 이상\) volatile로 표시 된 경우.|  
  
## 참고 항목  
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)   
 [THUNK\_ORDINAL 열거형](../../debugger/debug-interface-access/thunk-ordinal.md)