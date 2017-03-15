---
title: "IDebugCodeContext3::GetModule | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugCodeContext3::GetModule"
ms.assetid: 8e4317b8-8255-486c-a896-a68ed94f8aa1
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugCodeContext3::GetModule
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 모듈의 인터페이스에 대 한 참조를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetModule(   
   IDebugModule2 **ppModule  
);  
```  
  
```c#  
public int GetModule(   
   out IDebugModule2 ppModule  
);  
```  
  
#### 매개 변수  
 `ppModule`  
 \[out\] 디버그 모듈 인터페이스에 대 한 참조입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
 다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다 있는  **CDebugCodeContext** 를 노출 하는 개체는 [IDebugBeforeSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2.md) 인터페이스.  
  
```cpp#  
HRESULT CDebugCodeContext::GetModule(IDebugModule2** ppModule)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pModule;  
  
    IfFalseGo( ppModule, E_INVALIDARG );  
    *ppModule = NULL;  
  
    IfFailGo( this->GetModule(&pModule) );  
    IfFailGo( pModule->QueryInterface(IID_IDebugModule2, (void**) ppModule) );  
  
Error:  
  
    return hr;  
}  
```  
  
## 참고 항목  
 [IDebugCodeContext3](../../../extensibility/debugger/reference/idebugcodecontext3.md)