---
title: "IDebugComPlusSymbolProvider::IsFunctionDeleted | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugComPlusSymbolProvider::IsFunctionDeleted"
ms.assetid: b276bd25-6658-4898-bc36-04ecdf92aa2f
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugComPlusSymbolProvider::IsFunctionDeleted
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

함수에 지정 된 디버그 주소는 삭제를 확인 합니다.  
  
## 구문  
  
```cpp#  
HRESULT IsFunctionDeleted(  
   IDebugAddress* pAddress  
);  
```  
  
```c#  
int IsFunctionDeleted(  
   IDebugAddress pAddress  
);  
```  
  
#### 매개 변수  
 `pAddress`  
 \[in\] 디버그 주소를 표시 하는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  이 주소는 METHOD\_ADDRESS 이어야 합니다.  
  
## 반환 값  
 함수가 삭제 된 경우 반환 `S_OK`.  함수는 경우 존재를 반환 `S_FALSE`.  
  
## 예제  
 다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다 있는  **CDebugSymbolProvider** 를 노출 하는 개체는 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) 인터페이스.  
  
```cpp#  
HRESULT CDebugSymbolProvider::IsFunctionDeleted(  
    IDebugAddress* pAddress  
)  
{  
    HRESULT hr = S_OK;  
    CDEBUG_ADDRESS address;  
    CComPtr<CModule> pModule;  
  
    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));  
    ASSERT(IsValidInterfacePtr(pAddress, IDebugAddress));  
  
    METHOD_ENTRY( CDebugSymbolProvider::IsFunctionDeleted );  
  
    IfFalseGo( pAddress, S_FALSE );  
    IfFailGo( pAddress->GetAddress( &address ) );  
  
    ASSERT(address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD);  
    IfFalseGo( address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD, S_FALSE );  
  
    IfFailGo( GetModule( address.GetModule(), &pModule) );  
  
    if (!pModule->IsFunctionDeleted( address.addr.addr.addrMethod.tokMethod,  
                                     address.addr.addr.addrMethod.dwVersion,  
                                     address.addr.addr.addrMethod.dwOffset ))  
    {  
  
        // S_FALSE indicates the function is not deleted  
  
        hr = S_FALSE;  
    }  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::IsFunctionDeleted, hr );  
  
    if (!SUCCEEDED(hr))  
    {  
        hr = S_FALSE;  
    }  
  
    return hr;  
}  
```  
  
## 참고 항목  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)