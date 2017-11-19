---
title: "상수 (디버그 인터페이스 액세스 SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- constants, DIA SDK
- DIA SDK, constants
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50b6533b1036087dc8d0cdfe59b653774d781f55
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="constants-debug-interface-access-sdk"></a>상수(디버그 인터페이스 액세스 SDK)
DIA SDK를 통해 프로그램 디버그 데이터베이스 (PDB) 파일의 다양 한 섹션을 식별 하 이러한 문자열 상수를 사용할 수 있습니다.  
  
## <a name="constants"></a>상수  
 다음 C/c + + 매크로로 선언 됩니다.  
  
|매크로|값|  
|-----------|-----------|  
|`DiaTable_Symbols`|L "기호"|  
|`DiaTable_Sections`|L "섹션"|  
|`DiaTable_SrcFiles`|L "SourceFiles"|  
|`DiaTable_LineNums`|L "LineNumbers"|  
|`DiaTable_SegMap`|L "SegmentMap"|  
|`DiaTable_Dbg`|L "Dbg"|  
|`DiaTable_InjSrc`|L "InjectedSource"|  
|`DiaTable_FrameData`|L "FrameData"|  
  
## <a name="example"></a>예제  
 이러한 기호 중 하나를 사용 하는 예제는 다음과 같습니다.  
  
```C++  
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
  
## <a name="requirements"></a>요구 사항  
 헤더: dia2.h  
  
## <a name="see-also"></a>참고 항목  
 [참조](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)   
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)