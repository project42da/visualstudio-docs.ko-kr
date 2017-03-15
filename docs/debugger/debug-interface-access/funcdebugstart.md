---
title: "FuncDebugStart | Microsoft Docs"
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
  - "FuncDebugStart 기호"
  - "디버깅[DIA SDK], 시작점"
ms.assetid: 1cbc6ca5-87d0-4c30-a39e-0a9dc62ce1a9
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# FuncDebugStart
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

함수 정의 된 지점에 있는 디버깅 된 경우 시작, 소수점 기호에 의해 식별 됩니다 되는 `SymTagFuncDebugStart` 태그입니다.  
  
## 속성  
 다음 표에서이 기호 형식에 대해 유효한 속성을 보여 줍니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|일부 위치를 오프셋 합니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|위치 섹션 부분입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md).|  
|[IDiaSymbol::get\_customCallingConvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|`BOOL`|`TRUE`사용자 지정 호출 규칙 \(DIA SDK v 8.0에만 이상\)에서는 함수를 사용 하는 경우.|  
|[IDiaSymbol::get\_farReturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|`BOOL`|`TRUE`\(DIA SDK v 8.0에만 이상\)까지 반환 함수를 수행 하는 경우.|  
|[IDiaSymbol::get\_interruptReturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|`BOOL`|`TRUE`인터럽트 \(DIA SDK v 8.0에만 이상\)에서 반환 함수가 포함 된 경우.|  
|[IDiaSymbol::get\_isStatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|`BOOL`|`TRUE`\(DIA SDK v 8.0에만 이상\) 함수가 정적으로 표시 되는 경우.|  
|[IDiaSymbol::get\_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|바깥쪽 함수에 대 한 기호입니다.|  
|[IDiaSymbol::get\_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 심볼의 ID입니다.|  
|[IDiaSymbol::get\_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|시작점은 정적 위치를 있습니다. 자세한 내용은 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md).|  
|[IDiaSymbol::get\_noInline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|`BOOL`|`TRUE`함수에 지정 된 경우 해당 [noinline](/visual-cpp/cpp/noinline) 특성 \(DIA SDK v 8.0에만 이상\).|  
|[IDiaSymbol::get\_noReturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|`BOOL`|`TRUE`함수에 지정 된 경우 해당 [noreturn](/visual-cpp/cpp/noreturn) 특성 \(DIA SDK v 8.0에만 이상\).|  
|[IDiaSymbol::get\_notReached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|`BOOL`|`TRUE`\(DIA SDK v 8.0에만 이상\) 함수가 절대 호출 하는 경우.|  
|[IDiaSymbol::get\_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|메모리에서 오프셋입니다. 자세한 내용은 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md), `LocIsRegRel`.|  
|[IDiaSymbol::get\_optimizedCodeDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|`BOOL`|`TRUE`최적화 된 코드 \(DIA SDK v 8.0에만 이상\)의 디버그 정보는 코드에 있는 경우.|  
|[IDiaSymbol::get\_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|함수가 해당 블록 내에서 상대 위치입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagFuncDebugStart` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
|[IDiaSymbol::get\_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|함수 내에서 실행 파일의 위치입니다.|  
  
## 참고 항목  
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)   
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)