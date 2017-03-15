---
title: "레이블(디버그 인터페이스 액세스 SDK) | Microsoft Docs"
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
  - "위치, 프로그램 코드"
  - "레이블 기호"
ms.assetid: 8cef7620-5bc8-4500-8bd0-e9e638bccb24
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# 레이블(디버그 인터페이스 액세스 SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로그램 코드의 위치 식별 되는 `SymTagLabel` 기호입니다.  
  
## 속성  
 다음 표에서이 기호 형식에 대해 유효한 속성을 보여 줍니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|일부 위치를 오프셋 합니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|위치 섹션 부분입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_customCallingConvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|`TRUE`레이블을 사용자 지정 호출 규칙을 사용 하는 경우.|  
|[IDiaSymbol::get\_farReturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|`TRUE`레이블 까지는 반환 수행 하는 경우.|  
|[IDiaSymbol::get\_interruptReturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|`TRUE`인터럽트 반환 레이블 있는 경우입니다.|  
|[IDiaSymbol::get\_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|바깥쪽 컴파일, 블록 또는 함수에 대 한 기호입니다.|  
|[IDiaSymbol::get\_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 심볼의 ID입니다.|  
|[IDiaSymbol::get\_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|레이블 정적 위치를 있습니다. 자세한 내용은 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md) 열거형입니다.|  
|[IDiaSymbol::get\_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|레이블의 이름입니다.|  
|[IDiaSymbol::get\_noInline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|`TRUE`로 레이블이 지정 된 경우 해당 [noinline](/visual-cpp/cpp/noinline) 특성입니다.|  
|[IDiaSymbol::get\_noReturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|`TRUE`로 레이블이 지정 된 경우 해당 [noreturn](/visual-cpp/cpp/noreturn) 특성입니다.|  
|[IDiaSymbol::get\_notReached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|`TRUE`레이블을 절대로 호출 하는 경우.|  
|[IDiaSymbol::get\_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|메모리에서 오프셋입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md), `LocIsRegRel`.|  
|[IDiaSymbol::get\_optimizedCodeDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|`TRUE`코드 최적화 된 코드에 대 한 디버그 정보를 사용 하는 경우.|  
|[IDiaSymbol::get\_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|이 레이블은 해당 모듈 내에서 상대 위치입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagFuncDebugLabel` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
|[IDiaSymbol::get\_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|이 레이블은 실행 파일 이미지 내의 위치입니다.|  
  
## 참고 항목  
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)   
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)