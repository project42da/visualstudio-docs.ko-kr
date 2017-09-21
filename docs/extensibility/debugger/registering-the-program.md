---
title: "프로그램을 등록합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로그램을 등록"
  - "디버깅 [디버깅 SDK] 프로그램 등록"
ms.assetid: d726a161-7db3-4ef4-b258-9f6a5be68418
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 프로그램을 등록합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 엔진 포트를 가져온 후에 표시 되는 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) 인터페이스는 프로그램을 디버깅할 수 있도록 다음 단계입니다 포트를 등록 합니다.  등록 후 프로그램 다음과 같은 방법 중 하나를 사용 하 여 디버깅 하는 데 사용할 수 있습니다.  
  
-   디버거에서 실행 중인 응용 프로그램의 디버깅 완전히 제어 연결을 프로세스입니다.  
  
-   디버깅, 팩트 후 디버거가 독립적으로 실행 되는 프로그램의 디버깅을 위한 수 있도록 just\-in\-time \(JIT\).  런타임 아키텍처는 오류를 catch 하는 경우 디버거가 이전 운영 체제에 알립니다 또는 메모리 및 리소스 오류가 있는 프로그램의 런타임 환경에 릴리스 합니다.  
  
## 등록 절차  
  
#### 프로그램을 등록 하려면  
  
1.  호출의 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) 방법으로 포트를 구현 합니다.  
  
     `IDebugPortNotify2::AddProgramNode`필요에 대 한 포인터를 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스입니다.  
  
     일반적으로, 운영 체제 또는 런타임 환경 프로그램을 로드할 때 프로그램이 노드를 만듭니다.  디버그 엔진 \(DE\) 프로그램을 로드 하 라는 메시지가 표시 되는 경우는 DE 만듭니다 고 프로그램이 노드를 등록 합니다.  
  
     다음 예제 프로그램을 실행 하 고 포트를 등록 하는 디버그 엔진입니다.  
  
    > [!NOTE]
    >  시작 하 고 프로세스를 다시 시작 하는 유일한 방법은 아닙니다. 이 포트와 프로그램 등록은 주로 예입니다.  
  
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
 [포트를 시작합니다.](../../extensibility/debugger/getting-a-port.md)   
 [디버깅할 프로그램을 사용 하도록 설정](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)