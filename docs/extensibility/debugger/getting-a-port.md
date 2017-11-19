---
title: "포트 가져오기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, getting
- debugging [Debugging SDK], ports
ms.assetid: 745c2337-cfff-4d02-b49c-3ca7c4945c5e
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0645cefb4d102f976663bb4293454e2ae6318ad6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="getting-a-port"></a>포트 가져오기
포트는 프로세스가 실행 될 컴퓨터에 대 한 연결을 나타냅니다. 해당 컴퓨터를 로컬 컴퓨터나 원격 컴퓨터를 수 있습니다 (있는 가능 실행 될 수는 Windows 기반 운영 체제; 참조 [포트](../../extensibility/debugger/ports.md) 자세한 정보에 대 한).  
  
 포트를 나타내는 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) 인터페이스입니다. 포트에 연결 된 컴퓨터에서 실행 중인 프로세스에 대 한 정보를 얻을 사용 됩니다.  
  
 디버그 엔진 프로세스 정보에 대 한 요청을 충족 하 고 포트와 프로그램 노드를 등록 하기 위해 포트에 대 한 액세스를 해야 합니다. 예를 들어, 디버그 엔진 구현 하는 경우는 [IDebugProgramProvider2](../../extensibility/debugger/reference/idebugprogramprovider2.md) 인터페이스에 대 한 구현을 [GetProviderProcessData](../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) 메서드 필요한 프로세스는 포트를 요구할 수 정보를 반환 합니다.  
  
 Visual Studio 디버그 엔진에 필요한 포트에서 제공 하 고 포트 공급자에서이 포트를 가져옵니다. 프로그램에 연결 된 경우 (또는에서 디버거 내에서 예외로 인해 throw 되었으면 Just 시간 [JIT] 대화 상자를 트리거되어), 사용자는 사용할 전송 (포트 공급자에 대 한 다른 이름)의 옵션이 제공 됩니다. 그렇지 않으면 사용자가 디버거 내에서 프로그램 시작 되 면 프로젝트 시스템에서 사용할 포트 공급자를 지정 합니다. Visual Studio가 나타내는 포트 공급자를 인스턴스화하 하거나 이벤트에 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) 인터페이스를 하 고 새 포트를 호출 하 여 요청 [포트 추가](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 와 [ IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) 인터페이스입니다. 그러면이 포트 원본이 나 다른 한 가지 형태에 디버그 엔진에 전달 됩니다.  
  
## <a name="example"></a>예제  
 이 코드 조각에 제공 되는 포트를 사용 하는 방법을 보여 줍니다 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) 에서 프로그램 노드를 등록 하려면 [ResumeProcess](../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)합니다. 쉽게 구별할 수 있도록 직접 관련 되지 않은이 개념 매개 변수를 생략 했습니다.  
  
> [!NOTE]
>  이 예제에서는 시작 하 고 프로세스를 다시 시작 하는 포트를 사용 하 고 있다고 가정은 [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md) 인터페이스는 포트에서 구현 됩니다. 이 이러한 작업을 수행 하는 유일한 방법은 결코 수 있으며는 포트 하지도 참여할 이외의 다른 프로그램의 있어야 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 여기에 제공 합니다.  
  
```cpp  
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
  
## <a name="see-also"></a>참고 항목  
 [프로그램을 등록합니다.](../../extensibility/debugger/registering-the-program.md)   
 [디버깅할 프로그램을 사용 하도록 설정](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)   
 [포트 공급자](../../extensibility/debugger/port-suppliers.md)   
 [포트](../../extensibility/debugger/ports.md)