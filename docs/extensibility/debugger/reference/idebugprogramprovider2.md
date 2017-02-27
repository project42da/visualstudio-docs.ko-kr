---
title: "IDebugProgramProvider2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramProvider2"
helpviewer_keywords: 
  - "IDebugProgramProvider2 인터페이스"
ms.assetid: a9ec7b3e-a59c-4069-b2ee-6f45916eeb78
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# IDebugProgramProvider2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 등록 된 인터페이스 세션 디버그 매니저 \(SDM\) "를 통해 게시 된" 프로그램에 대 한 정보를 얻을 수 있습니다의 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md) 인터페이스입니다.  
  
## 구문  
  
```  
IDebugProgramProvider2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 디버깅 중인 프로그램에 대 한 정보를 제공 하기 위해이 인터페이스를 구현 합니다.  이 인터페이스는 DE 메트릭을 사용 하 여 레지스트리 섹션에 등록 된 `metricProgramProvider`에서 설명한 것 처럼, [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md).  
  
## 호출자에 대 한 참고 사항  
 COM의 호출 `CoCreateInstance` 기능을 `CLSID` 레지스트리에서 얻은 프로그램 공급자입니다.  이 예제를 참조 하십시오.  
  
## 메서드에서 Vtable 순서  
  
|메서드|설명|  
|---------|--------|  
|[GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)|프로그램을 실행 하 고 다양 한 방법으로 필터링 하는 방법에 대 한 정보를 얻습니다.|  
|[GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)|프로그램 노드를, 특정 프로세스 ID를 가져옵니다.|  
|[WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)|또한 특정 한 종류의 프로세스와 연결 된 공급자가 이벤트에 대 한 감시 하는 콜백을 설정 합니다.|  
|[SetLocale](../../../extensibility/debugger/reference/idebugprogramprovider2-setlocale.md)|DE에서 필요한 모든 언어 관련 리소스에 대 한 로캘을 설정 합니다.|  
  
## 설명  
 일반적으로 프로세스가이 인터페이스를 사용 하 여 해당 프로세스에서 실행 중인 프로그램에 대 한 확인 하십시오.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 예제  
  
```cpp#  
IDebugProgramProvider2 *GetProgramProvider(GUID *pDebugEngineGuid)  
{  
    // This is typically defined globally.  For this example, it is  
    // defined here.  
    static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0Exp";  
    IDebugProgramProvider2 *pProvider = NULL;  
    if (pDebugEngineGuid != NULL) {  
        CLSID clsidProvider = { 0 };  
        ::GetMetric(NULL,  
                    metrictypeEngine,  
                    *pDebugEngineGuid,  
                    metricProgramProvider,  
                    &clsidProvider,  
                    strRegistrationRoot);  
        if (!IsEqualGUID(clsidProvider,GUID_NULL)) {  
            CComPtr<IDebugProgramProvider2> spProgramProvider;  
            spProgramProvider.CoCreateInstance(clsidProvider);  
            if (spProgramProvider != NULL) {  
                pProvider = spProgramProvider.Detach();  
            }  
        }  
    }  
    return(pProvider);  
}  
```  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)