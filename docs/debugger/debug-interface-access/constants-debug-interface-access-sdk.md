---
title: "상수(디버그 인터페이스 액세스 SDK) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "상수, DIA SDK"
  - "DIA SDK, 상수"
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 상수(디버그 인터페이스 액세스 SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로그램 디버그 데이터베이스 \(PDB\) 파일 DIA SDK를 통해 다양 한 섹션을 확인 합니다 이러한 문자열 상수를 사용할 수 있습니다.  
  
## 상수  
 다음 C\/C\+\+ 매크로로 선언 됩니다.  
  
|매크로|값|  
|---------|-------|  
|`DiaTable_Symbols`|L "기호"|  
|`DiaTable_Sections`|L "구역"|  
|`DiaTable_SrcFiles`|L "SourceFiles"|  
|`DiaTable_LineNums`|L "LineNumbers"|  
|`DiaTable_SegMap`|"SegmentMap" L|  
|`DiaTable_Dbg`|L "Dbg"|  
|`DiaTable_InjSrc`|"InjectedSource" L|  
|`DiaTable_FrameData`|"FrameData" L|  
  
## 예제  
 이러한 기호 중 하나를 사용 하는 예는 다음과 같습니다.  
  
```cpp#  
HRESULT GetSymbolTable(IDiaEnumTables *pEnumTables, IDiaTable **pTable)  
{  
    HRESULT hr;  
    VARIANT var;  
    var.vt      = VT_BSTR;  
    var.bstrVal = SysAllocString( DiaTable_Symbols );  
    hr = pEnumTables->Item( var, pTable );  
    return(hr);  
}  
```  
  
## 요구 사항  
 헤더: dia2.h  
  
## 참고 항목  
 [참조](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)   
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)