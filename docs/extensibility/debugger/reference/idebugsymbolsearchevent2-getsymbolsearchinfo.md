---
title: "IDebugSymbolSearchEvent2::GetSymbolSearchInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugSymbolSearchEvent2::GetSymbolSearchInfo"
helpviewer_keywords: 
  - "IDebugSymbolSearchEvent2::GetSymbolSearchInfo"
ms.assetid: ae9eb72b-f2aa-43b8-87ca-da19d2e78d17
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugSymbolSearchEvent2::GetSymbolSearchInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

기호 로드 프로세스에 대 한 결과 검색 하는 이벤트 처리기가 호출 됩니다.  
  
## 구문  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
   IDebugModule3**    pModule,  
   BSTR*              pbstrDebugMessage,  
   MODULE_INFO_FLAGS* pdwModuleInfoFlags  
);  
```  
  
```c#  
int GetSymbolSearchInfo(  
   IDebugModule3              pModule,   
   ref string                 pbstrDebugMessage,   
   out enum_MODULE_INFO_FLAGS pdwModuleInfoFlags  
);  
  
```  
  
#### 매개 변수  
 `pModule`  
 \[out\] 해당 기호가 로드 된 모듈을 나타내는 IDebugModule3 개체입니다.  
  
 `pbstrDebugMessage`  
 \[in, out\] 모듈에서 오류 메시지를 포함 하는 문자열을 반환 합니다.  오류가 없는 경우에 모듈의 이름을이 문자열에만 포함 됩니다 있지만 비어.  
  
> [!NOTE]
>  \[C\+\+\] `pbstrDebugMessage` 수 없습니다 `NULL` 를 해제 해야 `SysFreeString`.  
  
 `pdwModuleInfoFlags`  
 \[out\] 플래그의 조합에서 [MODULE\_INFO\_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md) 기호가 로드 된 여부를 나타내는 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 처리기를 받는 시기는 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) 모듈에 대해 디버깅 기호를 로드 하려고 후 이벤트 처리기 해당 부하의 결과 확인 하려면 thismethod를 호출할 수 있습니다.  
  
## 참고 항목  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [MODULE\_INFO\_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md)   
 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)