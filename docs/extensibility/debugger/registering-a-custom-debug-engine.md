---
title: "사용자 지정 디버그 엔진을 등록합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "등록 하는 디버그 엔진"
ms.assetid: 9984cd3d-d34f-4662-9ace-31766499abf5
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# 사용자 지정 디버그 엔진을 등록합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 엔진 해야 COM 규칙 클래스 팩터리로 자체 등록할 뿐만 아니라 Visual Studio 레지스트리 하위 키를 통해 Visual Studio와 함께 등록 합니다.  
  
> [!NOTE]
>  일환으로 빌드되는 TextInterpreter 샘플에서는 디버그 엔진을 등록 하는 방법의 예를 찾을 수는 [Tutorial: Building a Debug Engine Using ATL COM](http://msdn.microsoft.com/ko-kr/9097b71e-1fe7-48f7-bc00-009e25940c24)합니다.  
  
## DLL 서버 프로세스  
 일반적으로 디버그 엔진 자체 DLL에서 COM 서버로 구현 됩니다. 즉, 디버그 엔진 등록 해야 해당 클래스 팩터리의 CLSID를 COM Visual Studio에서 액세스할 수 있습니다. 다음 디버그 엔진 해야 등록 자체 Visual Studio 자체와 모든 속성 \(메트릭 그렇지 않으면 라고도 함\)를 설정 하기 위해 디버그 엔진을 지원 합니다. 디버그 엔진은 지 원하는 기능에 따라 디버그 엔진에 대 한 Visual Studio 레지스트리 하위 키에 기록 되는 메트릭 선택 합니다.  
  
 [디버깅을 위한 SDK 도우미](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) 뿐만 아니라 레지스트리 위치에 디버그 엔진;를 등록 하는 데 필요한 설명 또한 다양 한 유용한 기능 및 보다 쉽게 레지스트리를 조작 하는 c \+ \+ 개발자에 대 한 선언을 포함 하는 dbgmetric.lib 라이브러리를 설명 합니다.  
  
### 예제  
 다음은 사용 하는 방법을 보여 주는 TextInterpreter 샘플\) \(에서 일반적인 예는 `SetMetric` Visual studio 디버그 엔진을 등록 하려면 \(dbgmetric.lib\)에서 작동 합니다. Dbgmetric.lib에 전달 되는 메트릭을 정의 됩니다.  
  
> [!NOTE]
>  TextInterpreter는 기본 디버그 엔진입니다. 구현 하지 않는\-따라서 등록 하지 않는 한 — 다른 기능. 전체 디버그 엔진의 전체 목록이 있을 `SetMetric` 하나 이상의 디버그 엔진은 각 기능에 대해 지 원하는 호출 또는 그에 상응 합니다.  
  
```  
// Define base registry subkey to Visual Studio.  
static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0";  
  
HRESULT CTextInterpreterModule::RegisterServer(BOOL bRegTypeLib, const CLSID * pCLSID)  
{  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricName, L"Text File", false, strRegistrationRoot);  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricCLSID, CLSID_Engine, false, strRegistrationRoot);  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricProgramProvider, CLSID_MsProgramProvider, false, strRegistrationRoot);  
  
    return base::RegisterServer(bRegTypeLib, pCLSID);  
}  
```  
  
## 참고 항목  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)   
 [디버깅을 위한 SDK 도우미](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Tutorial: Building a Debug Engine Using ATL COM](http://msdn.microsoft.com/ko-kr/9097b71e-1fe7-48f7-bc00-009e25940c24)