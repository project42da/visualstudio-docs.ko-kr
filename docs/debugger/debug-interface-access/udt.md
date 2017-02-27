---
title: "UDT | Microsoft Docs"
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
  - "SymTagUDT 기호"
  - "UDT(사용자 정의 형식) 기호"
  - "공용 구조체, 기호"
  - "UDT 기호"
  - "구조체[C++]"
ms.assetid: f12459dd-c64d-4cc9-9ee3-a56e19e9e573
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# UDT
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

각 클래스, 구조체 및 공용 구조체에서 식별 되는 `SymTagUDT` 기호입니다.  각 멤버, 함수, 데이터 또는 중첩 된 형식 및 각 기본 클래스의 사용자 정의 형식 \(UDT\) 클래스 하위 항목으로 나타납니다.  
  
## 속성  
 다음 표에서이 심볼 유형 추가 유효한 속성이 표시 됩니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|클래스 상위 있을 경우에 대 한 기호입니다.|  
|[IDiaSymbol::get\_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|부모 기호가 클래스의 ID입니다.|  
|[IDiaSymbol::get\_constructor](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|`BOOL`|`TRUE`UDT를 가진 생성자 인 경우.|  
|[IDiaSymbol::get\_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`UDT 상수로 표시 되는 경우.|  
|[IDiaSymbol::get\_hasAssignmentOperator](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|`BOOL`|`TRUE`UDT는 대입 연산자를 정의 된 경우.|  
|[IDiaSymbol::get\_hasCastOperator](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|`BOOL`|`TRUE`UDT를 정의 하는 캐스트 연산자가 있는 경우.|  
|[IDiaSymbol::get\_hasNestedTypes](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|`BOOL`|`TRUE`UDT는 중첩된 형식 정의가 포함 된 경우.|  
|[IDiaSymbol::get\_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`LONGLONG`|UDT의 바이트 단위에서 크기입니다.|  
|[IDiaSymbol::get\_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|바깥쪽 기호 [컴파일 대상](../../debugger/debug-interface-access/compiland.md).|  
|[IDiaSymbol::get\_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 심볼의 ID입니다.|  
|[IDiaSymbol::get\_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|UDT의 이름입니다.|  
|[IDiaSymbol::get\_nested](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|`BOOL`|`TRUE`UDT에서 중첩 되어 있는 경우입니다.|  
|[IDiaSymbol::get\_overloadedOperator](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|`BOOL`|`TRUE`UDT에 대해 오버 로드 된 연산자가 정의 된 경우.|  
|[IDiaSymbol::get\_packed](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|`BOOL`|`TRUE`UDT를 압축 하는 경우.|  
|[IDiaSymbol::get\_scoped](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|`BOOL`|`TRUE`비 글로벌 어휘 범위에서 UDT를 나타나는 경우입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagUDT` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
|[IDiaSymbol::get\_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|`DWORD`|이 구조체, 클래스 또는 공용 구조체 인지 여부를 나타냅니다. 자세한 내용은 [UdtKind 열거형](../../debugger/debug-interface-access/udtkind.md).|  
|[IDiaSymbol::get\_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`UDT 정렬 되지 않는 경우|  
|[IDiaSymbol::get\_virtualTableShape](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|`IDiaSymbol*`|가상 테이블 유형을 지정 합니다.|  
|[IDiaSymbol::get\_virtualTableShapeId](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|`DWORD`|가상 테이블 모양 심볼의 ID입니다.|  
|[IDiaSymbol::get\_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`UDT는 일시적으로 표시 된 경우.|  
  
## 참고 항목  
 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)