---
title: "IDebugSymbolProvider | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugSymbolProvider"
helpviewer_keywords: 
  - "IDebugSymbolProvider 인터페이스"
ms.assetid: df5f095f-1dee-46f9-84cf-92417c71d5fb
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugSymbolProvider
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 기호와 해당 필드로 반환 형식을 제공 하는 기호 공급자를 나타냅니다.  
  
## 구문  
  
```  
IDebugSymbolProvider : IUnknown  
```  
  
## 구현자 참고 사항  
 기호 공급자 기호를 입력 하 고 식 계산기에 정보를 입력 하기 위해이 인터페이스를 구현 해야 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스의 COM을 사용 하 여 가져온 `CoCreateInstance` 함수 \(관리 되지 않는 기호 공급자에 대 한\) 또는으로 적절 한 관리 코드 어셈블리를 로드 하 고 해당 어셈블리에서 발견 된 정보를 기반으로 하는 기호 공급자를 인스턴스화할.  디버그 엔진 식 계산기를 함께 작동 하도록 심볼 공급자를 인스턴스화합니다.  예를 들어이 인터페이스를 인스턴스화하는 방법 중 하나를 참조 하십시오.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugSymbolProvider`.  
  
|메서드|설명|  
|---------|--------|  
|`Initialize`|사용되지 않습니다.  사용하지 마십시오.|  
|`Uninitialize`|사용되지 않습니다.  사용하지 마십시오.|  
|[GetContainerField](../../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md)|디버그 주소가 포함 된 필드를 가져옵니다.|  
|`GetField`|사용되지 않습니다.  사용하지 마십시오.|  
|[GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)|문서 위치를에 배열 디버그 주소에 매핑합니다.|  
|[GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)|문서 컨텍스트를 배열 디버그 주소에 매핑합니다.|  
|[GetContextFromAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getcontextfromaddress.md)|문서 컨텍스트를 디버그 주소를 매핑합니다.|  
|[GetLanguage](../../../extensibility/debugger/reference/idebugsymbolprovider-getlanguage.md)|디버그 주소에서 코드를 컴파일하는 데 사용 된 언어를 가져옵니다.|  
|`GetGlobalContainer`|사용되지 않습니다.  사용하지 마십시오.|  
|[GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)|정규화 된 메서드 이름을 나타내는 필드를 가져옵니다.|  
|[GetClassTypeByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getclasstypebyname.md)|정규화 된 클래스 이름을 나타내는 클래스 필드 형식을 가져옵니다.|  
|[GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)|디버그 주소와 연결 된 네임 스페이스에 대 한 열거자를 만듭니다.|  
|[GetTypeByName](../../../extensibility/debugger/reference/idebugsymbolprovider-gettypebyname.md)|기호 이름을 기호 형식에 매핑합니다.|  
|[GetNextAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnextaddress.md)|메서드는 지정 된 디버그 주소 뒤에 오는 디버그 주소를 가져옵니다.|  
  
## 설명  
 이 인터페이스는 문서 위치 디버그 주소로 또는 그 반대로 매핑됩니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 예제  
 \(이 값을 알고 있어야 디버그 엔진의\) GUID를 지정 합니다. 기호 공급자를 인스턴스화하는 방법을 보여 주는이 예제입니다.  
  
```cpp#  
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
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)