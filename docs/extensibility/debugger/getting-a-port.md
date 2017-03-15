---
title: "포트를 시작합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "포트, 가져오기"
  - "디버깅 [디버깅 SDK], 포트"
ms.assetid: 745c2337-cfff-4d02-b49c-3ca7c4945c5e
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 포트를 시작합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로세스에서 실행 하는 컴퓨터에 연결이 된 포트를 나타냅니다.  해당 컴퓨터는 로컬 컴퓨터 또는 원격 컴퓨터 \(어떤 Windows 기반 운영 체제입니다; 가능한 경우 실행 될 수도 있습니다. 수 있습니다. 참조 하십시오 [포트](../../extensibility/debugger/ports.md) 에 대 한 더 많은 정보\).  
  
 포트를 통해 표시 됩니다 있는 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) 인터페이스입니다.  이 포트에 연결 된 컴퓨터에서 실행 중인 프로세스에 대 한 정보를 얻기 위해 사용 됩니다.  
  
 디버그 엔진 포트를 포트와 프로그램이 노드를 등록 하 고 프로세스 정보에 대 한 요청을 충족 시킬 수 있어야 합니다.  예를 들어, 디버그 엔진을 구현 하는 경우는 [IDebugProgramProvider2](../../extensibility/debugger/reference/idebugprogramprovider2.md) 인터페이스 구현에 대 한는 [GetProviderProcessData](../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) 메서드 반환 하 데 필요한 프로세스 정보에 대 한 포트 요청할 수 있습니다.  
  
 Visual Studio 디버그 엔진에 필요한 포트를 제공 하 고이 포트는 포트 공급자 로부터 입수.  프로그램에 연결 되어 있는 경우 \(또는에서 디버거 내에서 예외로 인해 되었습니다 발생 하면에서 Just\-in\-time \[JIT\] 대화 상자를 트리거하는\)에서 사용자가 전송 \(포트 공급자에 대 한 또 다른 이름\)을 선택 사용 하 여 부여 됩니다.  그렇지 않으면 사용자 프로그램에서 디버거를 시작 하는 경우 프로젝트 시스템 포트 공급자를 사용 하도록 지정 합니다.  이벤트에서 Visual Studio 표시 포트 공급자를 인스턴스화합니다는 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) 인터페이스, 및 새 포트를 호출 하 여 요청 [포트 추가](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 에 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) 인터페이스입니다.  이 포트 다음 디버그 엔진에 폼이 하나 또는 다른에 전달 됩니다.  
  
## 예제  
 이 코드 부분에 제공 된 포트를 사용 하는 방법을 보여 줍니다. [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) 노드 프로그램에 등록 하려면 [ResumeProcess](../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md).  이해를 돕기 위해 직접이 개념에 관련 된 매개 변수를 생략 했습니다.  
  
> [!NOTE]
>  포트를 사용 하 여 시작 하 고 프로세스를 다시 시작 하 고 가정이 예제는 [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md) 인터페이스의 포트에서 구현 됩니다.  포트도 이외의 다른 프로그램에 참여 하는 않는 것이 가능 하 고이 결코 이러한 작업을 수행 하는 유일한 방법입니다 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 를 지정 합니다.  
  
```cpp#  
// This is an IDebugEngineLaunch2 method.  
HRESULT CDebugEngine::LaunchSuspended(/* omitted parameters */,  
                                      IDebugPort2 *pPort,  
                                      /* omitted parameters */,  
                                      IDebugProcess2**ppDebugProcess)  
{  
    // do stuff here to set up for a launch (such as handling the other parameters)  
    ...  
  
    // Now get the IPortNotify2 interface so we can register a program node  
    // in CDebugEngine::ResumeProcess.  
    CComPtr<IDebugDefaultPort2> spDefaultPort;  
    HRESULT hr = pPort->QueryInterface(&spDefaultPort);  
    if (SUCCEEDED(hr))  
    {  
        CComPtr<IDebugPortNotify2> spPortNotify;  
        hr = spDefaultPort->GetPortNotify(&spPortNotify);  
        if (SUCCEEDED(hr))  
        {  
            // Remember the port notify so we can use it in ResumeProcess.  
            m_spPortNotify = spPortNotify;  
  
            // Now launch the process in a suspended state and return the  
            // IDebugProcess2 interface  
            CComPtr<IDebugPortEx2> spPortEx;  
            hr = pPort->QueryInterface(&spPortEx);  
            if (SUCCEEDED(hr))  
            {  
                // pass on the parameters we were given (omitted here)  
                hr = spPortEx->LaunchSuspended(/* omitted paramters */,ppDebugProcess)  
            }  
        }  
    }  
    return(hr);  
}  
  
HRESULT CDebugEngine::ResumeProcess(IDebugProcess2 *pDebugProcess)  
{  
    // Make a program node for this process  
    HRESULT hr;  
    CComPtr<IDebugProgramNode2> spProgramNode;  
    hr = this->GetProgramNodeForProcess(pProcess, &spProgramNode);  
    if (SUCCEEDED(hr))  
    {  
        hr = m_spPortNotify->AddProgramNode(spProgramNode);  
        if (SUCCEEDED(hr))  
        {  
            // resume execution of the process using the port given to us earlier.  
           // (Querying for the IDebugPortEx2 interface is valid here since  
           // that's how we got the IDebugPortNotify2 interface in the first place.)  
            CComPtr<IDebugPortEx2> spPortEx;  
            hr = m_spPortNotify->QueryInterface(&spPortEx);  
            if (SUCCEEDED(hr))  
            {  
                hr  = spPortEx->ResumeProcess(pDebugProcess);  
            }  
        }  
    }  
    return(hr);  
}  
```  
  
## 참고 항목  
 [프로그램을 등록합니다.](../../extensibility/debugger/registering-the-program.md)   
 [디버깅할 프로그램을 사용 하도록 설정](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)   
 [포트 공급자](../../extensibility/debugger/port-suppliers.md)   
 [포트](../../extensibility/debugger/ports.md)