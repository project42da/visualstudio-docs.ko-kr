---
title: "IDebugComPlusSymbolProvider::GetTypeFromAddress | Microsoft Docs"
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
  - "IDebugComPlusSymbolProvider::GetTypeFromAddress"
  - "GetTypeFromAddress"
ms.assetid: 01f21ff9-e8a5-4e5f-9f7b-1b6de8b1432f
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugComPlusSymbolProvider::GetTypeFromAddress
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

해당 디버그 주소 지정 기호 형식으로 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetTypeFromAddress(  
   IDebugAddress* pAddress,  
   IDebugField**  ppField  
);  
```  
  
```c#  
int GetTypeFromAddress(  
   IDebugAddress   pAddress,  
   out IDebugField ppField  
);  
```  
  
#### 매개 변수  
 `pAddress`  
 \[in\] 나타납니다 디버그 주소는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
 `ppField`  
 \[out\] 반환 배열 형식으로 표시 되는 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
 다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다 있는  **CDebugSymbolProvider** 를 노출 하는 개체는 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) 인터페이스.  
  
```cpp#  
HRESULT CDebugSymbolProvider::GetTypeFromAddress(  
    IDebugAddress *pAddress,  
    IDebugField **ppField)  
{  
    HRESULT hr = E_FAIL;  
    CDEBUG_ADDRESS da;  
    CDebugGenericParamScope* pGenScope = NULL;  
  
    METHOD_ENTRY( CDebugDynamicFieldSymbol::GetTypeFromPrimitive );  
  
    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));  
    ASSERT(IsValidWritePtr(ppField, IDebugField*));  
  
    IfFailGo( pAddress->GetAddress(&da) );  
  
    switch ( da.addr.dwKind )  
    {  
        case ADDRESS_KIND_METADATA_LOCAL:  
        case ADDRESS_KIND_METADATA_PARAM:  
        case ADDRESS_KIND_METADATA_FIELD:  
        case ADDRESS_KIND_METADATA_ARRAYELEM:  
        case ADDRESS_KIND_METADATA_METHOD:  
            {  
                IfFailGo( this->CreateClassType(da.GetModule(), da.tokClass, ppField) );  
                break;  
            }  
  
        case ADDRESS_KIND_METADATA_RETVAL:  
            {  
                if ( da.addr.addr.addrRetVal.dwCorType )  
                {  
  
                    IfNullGo( pGenScope = new CDebugGenericParamScope(da.GetModule(), da.tokClass, da.GetMethod()), E_OUTOFMEMORY );  
                    IfFailGo( this->CreateType((const COR_SIGNATURE*)(&da.addr.addr.addrRetVal.rgSig),  
                                               da.addr.addr.addrRetVal.dwSigSize,  
                                               da.GetModule(),  
                                               mdMethodDefNil,  
                                               pGenScope,  
                                               ppField) );  
                }  
                else  
                {  
                    IfFailGo( this->CreateClassType(da.GetModule(), da.tokClass, ppField) );  
                }  
  
                break;  
            }  
  
        default:  
            {  
                ASSERT(!"Address type not supported.");  
            }  
    }  
  
Error:  
  
    METHOD_EXIT( CDebugDynamicFieldSymbol::GetTypeFromPrimitive, hr );  
  
    RELEASE( pGenScope );  
  
    return hr;  
}  
```  
  
## 참고 항목  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)