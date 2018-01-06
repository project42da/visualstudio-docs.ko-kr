---
title: "썽크 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- thunk properties [DIA SDK]
- thunk symbol
ms.assetid: 01abb95f-d89a-465c-a4eb-8e8509598c95
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2dc847378510a6c7b0c07834a7658874f94b764e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="thunk"></a>썽크
각 `thunk` 으로 식별 되는 `SymTagThunk` 태그입니다.  
  
## <a name="properties"></a>속성  
 다음 표에서이 기호 형식에 대해 사용할 수 있는 속성을 보여 줍니다.  
  
|속성|데이터 형식|설명|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|액세스 한정자 특성 중 하나는 [CV_access_e 열거형](../../debugger/debug-interface-access/cv-access-e.md) 값 (DIA SDK v 8.0 이상 에서만에서).|  
|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|오프셋된 부분의 location; 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)합니다.|  
|[IDiaSegment::get_addressSection](../../debugger/debug-interface-access/idiasegment-get-addresssection.md)|`DWORD`|섹션 부분의 location; 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)합니다.|  
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|DIA SDK v 8.0 인 경우에 이상 있는 경우 클래스 부모를 포함 합니다.|  
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|바깥쪽 클래스 부모 기호 (DIA SDK v 8.0 이상 에서만에서)의 ID입니다.|  
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|TRUE 이면 썽크 상수 (DIA SDK v 8.0 이상 에서만에서)으로 표시 됩니다.|  
|[IDiaSymbol::get_intro](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|`BOOL`|TRUE 이면 썽크는 (DIA SDK v 8.0 이상 에서만에서)는 가상 함수에 대 한 소개|  
|[IDiaSymbol::get_isStatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|TRUE 이면 썽크 (DIA SDK v 8.0 이상 에서만에서) 정적 간주 됩니다.|  
|[IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|썽크의 코드의 바이트 수입니다.|  
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|바깥쪽 컴파일 대상, 블록 또는 함수에 대 한 기호입니다.|  
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 기호의 ID입니다.|  
|[IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|종단점이 있는 정적 location; 자세한 내용은 참조 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md) 열거 합니다.|  
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|썽크의 이름입니다.|  
|[IDiaSymbol::get_pure](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|`BOOL`|DIA SDK v 8.0에만 이상 썽크 완전히 가상 이면 TRUE입니다.|  
|[IDiaSymbol::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|모듈 내에서는이 썽크의 상대 위치입니다.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|기호 인덱스 ID입니다.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagThunk` (중 하나는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값).|  
|[IDiaSymbol::get_targetOffset](../../debugger/debug-interface-access/idiasymbol-get-targetoffset.md)|`DWORD`|오프셋된 부분 썽크 대상의 위치입니다.|  
|[IDiaSymbol::get_targetRelativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-targetrelativevirtualaddress.md)|`DWORD`|썽크 대상의 바깥쪽 블록의 상대 가상 주소입니다.|  
|[IDiaSymbol::get_targetSection](../../debugger/debug-interface-access/idiasymbol-get-targetsection.md)|`DWORD`|썽크 대상의 일부 섹션입니다.|  
|[IDiaSymbol::get_targetVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-targetvirtualaddress.md)|`ULONGLONG`|실행 가능 이미지에서 썽크 대상의 위치입니다.|  
|[IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)|`DWORD`|에 정의 된 대로 형식을 썽크는 [THUNK_ORDINAL 열거형](../../debugger/debug-interface-access/thunk-ordinal.md)합니다.|  
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|이 썽크 (DIA SDK v 8.0 이상 에서만에서)의 형식입니다.|  
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|기호 형식 (DIA SDK v 8.0 이상 에서만에서)의 ID입니다.|  
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`썽크 (DIA SDK v 8.0 이상 에서만에서), 정렬 되지 않은 경우|  
|[IDiaSymbol::get_virtual](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|`BOOL`|`TRUE`이면 썽크 가상 (DIA SDK v 8.0 이상 에서만에서).|  
|[IDiaSymbol::get_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|이 썽크 실행 가능 이미지 내에서 위치입니다.|  
|[IDiaSymbol::get_virtualBaseOffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|`DWORD`|이 썽크 (DIA SDK v 8.0에만 또는 이상)를 가상 테이블의 오프셋입니다.|  
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`경우 썽크 (DIA SDK v 8.0 이상 에서만에서) volatile로 표시 되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)   
 [THUNK_ORDINAL 열거형](../../debugger/debug-interface-access/thunk-ordinal.md)