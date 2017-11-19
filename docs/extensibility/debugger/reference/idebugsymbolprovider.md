---
title: IDebugSymbolProvider | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugSymbolProvider
helpviewer_keywords: IDebugSymbolProvider interface
ms.assetid: df5f095f-1dee-46f9-84cf-92417c71d5fb
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 33958c7159c6348aca696e295deb245031e904d4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugsymbolprovider"></a>IDebugSymbolProvider
이 인터페이스는 기호 및 필드로 반환 하기 형식을 제공 하는 기호 공급자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugSymbolProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자 기호를 입력 하 고 식 계산기에 대 한 정보를 입력 하려면이 인터페이스를 구현 해야 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스는 COM의를 사용 하 여 얻은 `CoCreateInstance` 함수 (관리 되지 않는 기호 공급자)에 대 한 적절 한 로드 하 여 관리 코드 어셈블리 및 해당 어셈블리에서 발견 한 정보를 기반으로 기호 공급자를 인스턴스화하면 합니다. 디버그 엔진 식 계산기 함께에서 작동 하도록 기호 공급자를 인스턴스화합니다. 이 인터페이스를 인스턴스화하는 한 가지 방법은 예제를 참조 하세요.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugSymbolProvider`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|`Initialize`|더 이상 사용되지 않습니다. 사용하지 마십시오.|  
|`Uninitialize`|더 이상 사용되지 않습니다. 사용하지 마십시오.|  
|[GetContainerField](../../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md)|디버그 주소를 포함 하는 필드를 가져옵니다.|  
|`GetField`|더 이상 사용되지 않습니다. 사용하지 마십시오.|  
|[GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)|디버그 주소 배열로 문서 위치를 매핑합니다.|  
|[GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)|디버그 주소 배열로 문서 컨텍스트를 매핑합니다.|  
|[GetContextFromAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getcontextfromaddress.md)|문서 컨텍스트로 디버그 주소를 매핑합니다.|  
|[GetLanguage](../../../extensibility/debugger/reference/idebugsymbolprovider-getlanguage.md)|디버그 주소에서 코드를 컴파일하는 데 사용 되는 언어를 가져옵니다.|  
|`GetGlobalContainer`|더 이상 사용되지 않습니다. 사용하지 마십시오.|  
|[GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)|정규화 된 메서드 이름을 나타내는 필드를 가져옵니다.|  
|[GetClassTypeByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getclasstypebyname.md)|정규화 된 클래스 이름을 나타내는 클래스 필드 형식을 가져옵니다.|  
|[GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)|디버그 주소와 연결 된 네임 스페이스에 대 한 열거자를 만듭니다.|  
|[GetTypeByName](../../../extensibility/debugger/reference/idebugsymbolprovider-gettypebyname.md)|기호 형식 기호 이름을 매핑합니다.|  
|[GetNextAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnextaddress.md)|메서드에서 지정 된 디버그 주소 다음에 나오는 디버그 주소를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 그 반대의 디버그 주소에 문서 위치를 매핑합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>예제  
 이 예제에는 GUID (디버그 엔진이이 값을 알고 있어야)를 지정 된 기호 공급자를 인스턴스화하는 방법을 보여 줍니다.  
  
```cpp  
// A debug engine uses its own symbol provider and would know the GUID  
// of that provider.  
IDebugSymbolProvider *GetSymbolProvider(GUID *pSymbolProviderGuid)  
{  
    // This is typically defined globally.  For this example, it is  
    // defined here.  
    static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0Exp";  
    IDebugSymbolProvider *pProvider = NULL;  
    if (pSymbolProviderGuid != NULL) {  
        CLSID clsidProvider = { 0 };  
        ::GetSPMetric(*pSymbolProviderGuid,  
                      storetypeFile,  
                      metricCLSID,  
                      &clsidProvider,  
                      strRegistrationRoot);  
        if (IsEqualGUID(clsidProvider,GUID_NULL)) {  
            // No file type provider, try metadata provider.  
            ::GetSPMetric(*pSymbolProviderGuid,  
                          ::storetypeMetadata,  
                          metricCLSID,  
                          &clsidProvider,  
                          strRegistrationRoot);  
        }  
        if (!IsEqualGUID(clsidProvider,GUID_NULL)) {  
            CComPtr<IDebugSymbolProvider> spSymbolProvider;  
            spSymbolProvider.CoCreateInstance(clsidProvider);  
            if (spSymbolProvider != NULL) {  
                pProvider = spSymbolProvider.Detach();  
            }  
        }  
    }  
    return(pProvider);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)