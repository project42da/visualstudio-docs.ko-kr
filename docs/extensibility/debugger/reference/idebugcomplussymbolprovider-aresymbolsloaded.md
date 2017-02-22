---
title: "IDebugComPlusSymbolProvider::AreSymbolsLoaded | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "AreSymbolsLoaded"
  - "IDebugComPlusSymbolProvider::AreSymbolsLoaded"
ms.assetid: bbf8707d-f89c-4177-b019-d519f1ec6f4a
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugComPlusSymbolProvider::AreSymbolsLoaded
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

응용 프로그램 도메인 식별자를 지정 합니다. 지정 된 모듈에 대해 디버그 기호가 로드 되었는지 확인 합니다.  
  
## 구문  
  
```cpp#  
HRESULT AreSymbolsLoaded (  
   ULONG32 ulAppDomainID,  
   GUID    guidModule  
);  
```  
  
```c#  
int AreSymbolsLoaded (  
   uint ulAppDomainID,  
   Guid guidModule  
);  
```  
  
#### 매개 변수  
 `ulAppDomainID`  
 \[in\] 응용 프로그램 도메인 식별자입니다.  
  
 `guidModule`  
 \[in\] 모듈에 대 한 고유 식별자입니다.  
  
## 반환 값  
 디버그 기호가 로드 되지 않으면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE`.  
  
## 예제  
 다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다 있는  **CDebugSymbolProvider** 를 노출 하는 개체는 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) 인터페이스.  
  
```cpp#  
HRESULT CDebugSymbolProvider::AreSymbolsLoaded(  
    ULONG32 ulAppDomainID,  
    GUID guidModule  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pModule;  
    Module_ID idModule(ulAppDomainID, guidModule);  
  
    METHOD_ENTRY( CDebugSymbolProvider::AreSymbolsLoaded );  
  
    IfFalseGo( GetModule( idModule, &pModule ) == S_OK, S_FALSE );  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::AreSymbolsLoaded, hr );  
    return hr;  
}  
```  
  
## 참고 항목  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)