---
title: IDebugSymbolSearchEvent2::GetSymbolSearchInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
helpviewer_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
ms.assetid: ae9eb72b-f2aa-43b8-87ca-da19d2e78d17
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 518429149ad1d997b860e486f3db4e519ef42cae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugsymbolsearchevent2getsymbolsearchinfo"></a>IDebugSymbolSearchEvent2::GetSymbolSearchInfo
기호 로드 프로세스에 대 한 결과 검색 하는 이벤트 처리기에서 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
   IDebugModule3**    pModule,  
   BSTR*              pbstrDebugMessage,  
   MODULE_INFO_FLAGS* pdwModuleInfoFlags  
);  
```  
  
```csharp  
int GetSymbolSearchInfo(  
   IDebugModule3              pModule,   
   ref string                 pbstrDebugMessage,   
   out enum_MODULE_INFO_FLAGS pdwModuleInfoFlags  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pModule`  
 [out] 기호가 로드 않은 모듈을 나타내는 IDebugModule3 개체입니다.  
  
 `pbstrDebugMessage`  
 [out에서] 모듈에서 모든 오류 메시지를 포함 하는 문자열을 반환 합니다. 오류가 없는, 그런 다음이 문자열은 모듈의 이름을 포함 있지만 비어 있지 않습니다.  
  
> [!NOTE]
>  [C + +] `pbstrDebugMessage` 안 `NULL` 으로 해제 해야 `SysFreeString`합니다.  
  
 `pdwModuleInfoFlags`  
 [out] 플래그의 조합 된 [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md) 기호가 로드 된 여부를 나타내는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 처리기를 받을 때의 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) 모듈에 대 한 디버깅 기호를 로드 하려고 시도 후에 이벤트, 처리기 해당 부하의 결과 얻기 위해이 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md)   
 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)