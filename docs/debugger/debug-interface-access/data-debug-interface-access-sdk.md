---
title: "데이터(디버그 인터페이스 액세스 SDK) | Microsoft Docs"
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
  - "전역 변수[C++], 기호로"
  - "지역 변수[C++], 기호로"
  - "클래스 멤버[C++], 기호로"
  - "데이터 기호"
ms.assetid: 0f17e96a-2e06-42c9-a877-3e5e670ee0ef
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# 데이터(디버그 인터페이스 액세스 SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

모든 변수, 매개 변수, 지역 변수, 전역 변수 및 클래스 멤버와 같은 식별 됩니다 `SymTagData` 기호입니다.  상수 값 \(`LocIsConstant`\)는이 형식으로 식별 됩니다.  
  
## 속성  
 다음 표에서이 기호 형식에 대해 유효한 속성을 보여 줍니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|필드의 경우 다음 값 중 하나를 [CV\_access\_e 열거형](../../debugger/debug-interface-access/cv-access-e.md).|  
|[IDiaSymbol::get\_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|일부 위치를 오프셋 합니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|위치 섹션 부분입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_addressTaken](../../debugger/debug-interface-access/idiasymbol-get-addresstaken.md)|`BOOL`|`TRUE`이 데이터의이 주소가 다른 기호로 참조 되는 경우.|  
|[IDiaSymbol::get\_bitPosition](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)|`DWORD`|위치 비트 위치입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) \(DIA SDK v 8.0에서는 지원 되지 않음\).|  
|[IDiaSymbol::get\_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|이 경우 클래스, 구조체, 공용 구조체 또는 클래스 필드 수 있습니다.|  
|[IDiaSymbol::get\_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|부모 기호가 클래스의 ID입니다.|  
|[IDiaSymbol::get\_compilerGenerated](../../debugger/debug-interface-access/idiasymbol-get-compilergenerated.md)|`BOOL`|`TRUE`데이터는 컴파일러에 의해 생성 된 경우.|  
|[IDiaSymbol::get\_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`데이터 상수로 표시 되어 있는 경우입니다.|  
|[IDiaSymbol::get\_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|`DWORD`|[DataKind 열거형](../../debugger/debug-interface-access/datakind.md) 값 중 하나입니다.|  
|[IDiaSymbol::get\_isAggregated](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)|`BOOL`|`TRUE`데이터 \(DIA SDK v 8.0에만 및 나중에\) 하는 집계 된 데이터 형식에 포함 된 경우.|  
|[IDiaSymbol::get\_isSplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)|`BOOL`|`TRUE`데이터가 있으면 DIA SDK v 8.0 에서만에서 나중에 여러 심볼의 집합체로 나눌 수 있습니다.|  
|[IDiaSymbol::get\_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|비트 필드의 길이입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|기호는 바깥쪽 컴파일, 함수, 또는 블록입니다.|  
|[IDiaSymbol::get\_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 심볼의 ID입니다.|  
|[IDiaSymbol::get\_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|모든 허용 된 위치 형식입니다. 자세한 내용은 참조 하십시오.[기호 위치](../../debugger/debug-interface-access/symbol-locations.md)|  
|[IDiaSymbol::get\_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|변수의 이름입니다.|  
|[IDiaSymbol::get\_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|레지스터 내용에서 오프셋입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_registerId](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|`DWORD`|위치 지정자를 등록 합니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|데이터는 블록 내에서 상대적 위치입니다.|  
|[IDiaSymbol::get\_slot](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|`DWORD`|데이터 슬롯 수를 가져옵니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagData` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
|[IDiaSymbol::get\_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|`DWORD`|데이터를 나타내는 메타 데이터 토큰입니다.|  
|[IDiaSymbol::get\_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|기호는 변수 형식입니다.|  
|[IDiaSymbol::get\_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|변수 형식 기호 ID입니다.|  
|[IDiaSymbol::get\_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`데이터 정렬 된 경우.|  
|[IDiaSymbol::get\_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|`VARIANT`|상수 데이터의 값입니다.|  
|[IDiaSymbol::get\_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|실행 파일 내에서 데이터의 위치입니다.|  
|[IDiaSymbol::get\_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`일시적으로 데이터를 표시 하는 경우.|  
  
## 참고 항목  
 [CV\_access\_e 열거형](../../debugger/debug-interface-access/cv-access-e.md)   
 [DataKind 열거형](../../debugger/debug-interface-access/datakind.md)   
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)   
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)