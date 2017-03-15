---
title: "FunctionType | Microsoft Docs"
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
  - "함수 시그니처"
  - "FunctionType 기호"
ms.assetid: 646a07e7-9d4f-4e21-95e3-3e403cdd4843
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# FunctionType
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

각 고유 함수 서명을 식별 되는 `SymTagFunctionType` 기호입니다.  각 매개 변수 클래스 하위 기호로 구분 됩니다 있는 `SymTagFunctionArgType` 태그입니다.  
  
## 속성  
 다음 표에서이 심볼 유형 추가 유효한 속성이 표시 됩니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)|`DWORD`|값 중 하나를 [CV\_call\_e 열거형](../../debugger/debug-interface-access/cv-call-e.md).|  
|[IDiaSymbol::get\_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|이 함수 \(또는 메서드\)의 구성원 인지 클래스입니다.|  
|[IDiaSymbol::get\_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|부모 기호가 클래스의 ID입니다.|  
|[IDiaSymbol::get\_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`함수는 상수로 표시 된 경우.|  
|[IDiaSymbol::get\_count](../../debugger/debug-interface-access/idiasymbol-get-count.md)|`DWORD`|함수 매개 변수 개수입니다.|  
|[IDiaSymbol::get\_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|바깥쪽 컴파일 대상의 기호입니다.|  
|[IDiaSymbol::get\_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 심볼의 ID입니다.|  
|[IDiaSymbol::get\_objectPointerType](../../debugger/debug-interface-access/idiasymbol-get-objectpointertype.md)|`IDiaSymbol*`|형식 메서드 개체 포인터 \("this"\)입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagFunctionType` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
|[IDiaSymbol::get\_thisAdjust](../../debugger/debug-interface-access/idiasymbol-get-thisadjust.md)|`LONG`|"이"이 조정기 메서드의 논리입니다.|  
|[IDiaSymbol::get\_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|반환 값 형식에 대 한 기호입니다.|  
|[IDiaSymbol::get\_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID 유형 기호입니다.|  
|[IDiaSymbol::get\_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`이면 함수는 정렬 되지 않습니다.|  
|[IDiaSymbol::get\_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`함수에서 일시적으로 표시 된 경우.|  
  
## 참고 항목  
 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [CV\_access\_e 열거형](../../debugger/debug-interface-access/cv-access-e.md)   
 [FunctionArgType](../../debugger/debug-interface-access/functionargtype.md)