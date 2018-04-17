---
title: 엔진을 디버그 하는 사용자 지정 등록 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, registering
ms.assetid: 9984cd3d-d34f-4662-9ace-31766499abf5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 99ff41f116e569baaae312acd17408928a6c79f4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="registering-a-custom-debug-engine"></a>사용자 지정 디버그 엔진을 등록 하는 중
디버그 엔진 해야 COM 규칙을 따르는 클래스 팩터리로 자신을 등록할 뿐만 아니라 Visual Studio 레지스트리 하위 키를 통해 Visual Studio와 함께 등록 합니다.  
  
> [!NOTE]
>  일부분으로 빌드되는 TextInterpreter 샘플에서 디버그 엔진을 등록 하는 방법의 예를 확인할 수 있습니다는 [자습서: 빌드는 디버그 엔진 사용 하 여 ATL COM](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24)합니다.  
  
## <a name="dll-server-process"></a>DLL 서버 프로세스  
 일반적으로 디버그 엔진 자체 DLL에 COM 서버로 구현 됩니다. 즉, 디버그 엔진 등록 해야 해당 클래스 팩터리의 CLSID를 COM Visual Studio에서 액세스할 수 있습니다. 다음 디버그 엔진에 등록 해야 자체 Visual Studio 자체 (그렇지 않으면이 라고 메트릭) 속성을 설정 하기 위해 디버그 엔진을 지원 합니다. 디버그 엔진을 지 원하는 기능에 따라 디버그 엔진에 대 한 Visual Studio 레지스트리 하위 키에 기록 되는 메트릭을 선택 합니다.  
  
 [디버깅에 대 한 SDK 도우미](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) 위치를 설명 뿐만 아니라 레지스트리 디버그 엔진;을 등록 하는 데 필요한 다양 한 유용한 함수가 및 구성 하는 c + + 개발자에 대 한 선언을 포함 하는 dbgmetric.lib 라이브러리에 대해서도 설명 보다 쉽게 레지스트리를 조작 합니다.  
  
### <a name="example"></a>예제  
 다음은 사용 하는 방법을 보여 주는 (TextInterpreter 샘플)에서 일반적인 예로 `SetMetric` Visual Studio와 함께 디버그 엔진을 등록 하려면 (dbgmetric.lib)에서 작동 합니다. 전달 되는 메트릭은 dbgmetric.lib에도 정의 합니다.  
  
> [!NOTE]
>  TextInterpreter는 기본 디버그 엔진; 구현 하지 않으므로-따라서 등록 하지 않는 및-다른 기능입니다. 보다 완전 디버그 엔진으로는 전체 목록이 `SetMetric` 하나 이상의 디버그 엔진은 각 기능에 대해 지 원하는 호출 또는 그에 상응 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)   
 [디버깅을 위한 도우미 SDK](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [자습서: ATL COM을 사용 하 여 디버그 엔진을 구축](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24)