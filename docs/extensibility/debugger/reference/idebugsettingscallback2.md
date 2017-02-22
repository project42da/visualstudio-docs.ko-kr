---
title: "IDebugSettingsCallback2 | Microsoft Docs"
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
  - "IDebugSettingsCallback2 인터페이스"
ms.assetid: 7e525d0b-7d7a-4d1c-8b78-e1398fa922f2
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugSettingsCallback2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 미터법 설정을 읽을 수 있도록 원격으로 합니다.  
  
## 구문  
  
```  
IDebugSettingsCallback2D : IUnknown  
```  
  
## 구현자 참고 사항  
 이 인터페이스 디버그 세션 관리자의 이벤트 콜백으로 구현 되 고 디버깅 엔진으로 사용 합니다.  로컬 Dbgmetric \[d\].lib 대신 사용할 수도 있습니다.  
  
## 메서드  
 다음 표에서 메서드를 `IDebugSettingsCallback2`.  
  
|메서드|설명|  
|---------|--------|  
|[EnumEEs](../../../extensibility/debugger/reference/idebugsettingscallback2-enumees.md)|공급 업체 및 언어 식별자를 지정 합니다. 사용할 수 있는 식 계산기를 열거 합니다.|  
|[GetEELocalObject](../../../extensibility/debugger/reference/idebugsettingscallback2-geteelocalobject.md)|메트릭이 주어진 식 계산기 로컬 개체를 검색 합니다.|  
|[GetEEMetricDword](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricdword.md)|지정 된 메트릭이 식 계산기에 해당 하는 값을 검색 합니다.|  
|[GetEEMetricFile](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricfile.md)|이름 또는 메트릭을 지정 식 계산기 메트릭 파일을 검색 합니다.|  
|[GetEEMetricGuid](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricguid.md)|식 평가기 메트릭 지정 된 이름에 대 한 고유 식별자를 검색 합니다.|  
|[GetEEMetricString](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricstring.md)|지정 된 이름에 식 계산기 메트릭 값 문자열을 검색 합니다.|  
|[GetMetricDword](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricdword.md)|메트릭 지정 된 이름 값을 검색 합니다.|  
|[GetMetricGuid](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricguid.md)|지정 된 이름에 미터법의 고유 식별자를 검색 합니다.|  
|[GetMetricString](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricstring.md)|지정 된 이름 메트릭 값 문자열을 검색 합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 예제  
 다음 예제에서는 사용 하는 함수는  **IDebugSettingsCallback2** 개체를 매개 변수로.  
  
```cpp#  
HRESULT GetDebugSettingsCallback (IDebugSettingsCallback2 **ppCallback)  
{  
    HRESULT hRes = E_FAIL;  
  
    if ( ppCallback )  
   {  
        if ( EVAL(m_pdec) )  
            hRes = m_pdec->QueryInterface(IID_IDebugSettingsCallback2, (void **)ppCallback);  
        else  
            hRes = E_FAIL;  
    }  
    else  
        hRes = E_INVALIDARG;  
  
    return ( hRes );  
}  
```