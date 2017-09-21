---
title: "IDebugExpressionEvaluator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpressionEvaluator"
helpviewer_keywords: 
  - "IDebugExpressionEvaluator 인터페이스"
ms.assetid: 0636d8c3-625a-49fa-94b6-516f22b7e1bc
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# IDebugExpressionEvaluator
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스는 식 계산기를 나타냅니다.  
  
## 구문  
  
```  
IDebugExpressionEvaluator : IUnknown  
```  
  
## 구현자를 위한 정보  
 식 계산기는이 인터페이스를 구현 해야 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 가져오려면 인스턴스화를 통해 식 계산기는 `CoCreateInstance` 계산기의 클래스 ID \(CLSID\)를 사용 하 여 메서드. 예제를 참조 하십시오.  
  
## Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugExpressionEvaluator`합니다.  
  
|메서드|설명|  
|---------|--------|  
|[구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)|식 문자열을 구문 분석 된 식으로 변환합니다.|  
|[GetMethodProperty](../../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md)|지역 변수, 인수 및 기타 속성 메서드를 가져옵니다.|  
|[GetMethodLocationProperty](../../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodlocationproperty.md)|메서드 위치와 오프셋 메모리 주소를 변환합니다.|  
|[SetLocale](../../../extensibility/debugger/reference/idebugexpressionevaluator-setlocale.md)|인쇄 가능한 결과 만드는 데 사용할 언어를 결정 합니다.|  
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugexpressionevaluator-setregistryroot.md)|레지스트리 루트를 설정합니다. Side\-by\-side\-디버깅에 사용 합니다.|  
  
## 설명  
 호출 하는 디버그 엔진 \(DE\) 인스턴스화합니다 \(EE\) 식 계산기는 일반적인 상황에서 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)합니다. 레지스트리에서 DE EE의 CLSID를 가져옵니다는 DE에 맞는 언어 및 공급 업체에 사용 하려는 EE 알고, 있기 때문에 \(의 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) 함수 `GetEEMetric`, 이 검색을 사용할 때 도움이\).  
  
 EE 인스턴스화되는 DE 호출 [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 식을 구문 분석에 저장 하는 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) 개체입니다. 나중에 대 한 호출 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) 식을 계산 합니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 예제  
 이 예제에는 소스 코드의 기호 공급자 및 주소를 제공 하는 식 계산기를 인스턴스화하는 방법을 보여 줍니다. 이 예제에서는 함수를 사용 하 여 `GetEEMetric`, 에서 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) 라이브러리, dbgmetric.lib 합니다.  
  
```cpp#  
IDebugExpressionEvaluator GetExpressionEvaluator(IDebugSymbolProvider pSymbolProvider,  
                                                 IDebugAddress *pSourceAddress)  
{  
    // This is typically defined globally but is specified here just  
    // for this example.  
    static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0Exp";  
  
    IDebugExpressionEvaluator *pEE = NULL;  
    if (pSymbolProvider != NULL && pSourceAddress != NULL) {  
        HRESULT hr         = S_OK;  
        GUID  languageGuid = { 0 };  
        GUID  vendorGuid   = { 0 };  
  
        hr = pSymbolProvider->GetLanguage(pSourceAddress,  
                                          &languageGuid,  
                                          &vendorGuid);  
        if (SUCCEEDED(hr)) {  
            CLSID clsidEE      = { 0 };  
            CComPtr<IDebugExpressionEvaluator> spExpressionEvaluator;  
            // Get the expression evaluator's CLSID from the registry.  
            ::GetEEMetric(languageGuid,  
                          vendorGuid,  
                          metricCLSID,  
                          &clsidEE,  
                          strRegistrationRoot);  
            if (!IsEqualGUID(clsidEE,GUID_NULL)) {  
                // Instantiate the expression evaluator.  
                spExpressionEvaluator.CoCreateInstance(clsidEE);  
            }  
            if (spExpressionEvaluator != NULL) {  
                pEE = spExpressionEvaluator.Detach();  
            }  
        }  
    }  
    return pEE;  
}  
```  
  
## 참고 항목  
 [식 평가 인터페이스](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)