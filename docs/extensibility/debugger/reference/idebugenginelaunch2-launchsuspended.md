---
title: "IDebugEngineLaunch2::LaunchSuspended | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngineLaunch2::LaunchSuspended"
helpviewer_keywords: 
  - "IDebugEngineLaunch2::LaunchSuspended"
ms.assetid: 5dd2643e-c20a-470e-9024-2a423eb39856
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEngineLaunch2::LaunchSuspended
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 프로세스 디버그 엔진 \(DE\)으로 시작합니다.  
  
## 구문  
  
```cpp#  
HRESULT LaunchSuspended (   
   LPCOLESTR             pszMachine,  
   IDebugPort2*          pPort,  
   LPCOLESTR             pszExe,  
   LPCOLESTR             pszArgs,  
   LPCOLESTR             pszDir,  
   BSTR                  bstrEnv,  
   LPCOLESTR             pszOptions,  
   LAUNCH_FLAGS          dwLaunchFlags,  
   DWORD                 hStdInput,  
   DWORD                 hStdOutput,  
   DWORD                 hStdError,  
   IDebugEventCallback2* pCallback,  
   IDebugProcess2**      ppDebugProcess  
);  
```  
  
```c#  
int LaunchSuspended(  
   string               pszServer,   
   IDebugPort2          pPort,   
   string               pszExe,   
   string               pszArgs,   
   string               pszDir,   
   string               bstrEnv,   
   string               pszOptions,   
   enum_LAUNCH_FLAGS    dwLaunchFlags,   
   uint                 hStdInput,   
   uint                 hStdOutput,   
   uint                 hStdError,  
   IDebugEventCallback2 pCallback,   
   out IDebugProcess2   ppProcess  
);  
```  
  
#### 매개 변수  
 `pszMachine`  
 \[in\] 프로세스를 실행 하는 컴퓨터의 이름입니다.  Null 값을 사용 하 여 로컬 컴퓨터를 지정 합니다.  
  
 `pPort`  
 \[in\] [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 인터페이스 프로그램을 실행 하는 포트를 표시 합니다.  
  
 `pszExe`  
 \[in\] 실행 될 실행 파일의 이름입니다.  
  
 `pszArgs`  
 \[in\] 실행 파일에 전달할 인수입니다.  인수가 없으면 null 값을 수 있습니다.  
  
 `pszDir`  
 \[in\] 실행 파일에서 사용 되는 작업 디렉터리의 이름입니다.  필요한 작업 디렉터리가 없는 경우 null 값을 수 있습니다.  
  
 `bstrEnv`  
 \[in\] 환경 블록의 NULL로 끝나는 문자열 뒤에 추가 NULL 종결자가 있습니다.  
  
 `pszOptions`  
 \[in\] 실행 파일에 대 한 옵션입니다.  
  
 `dwLaunchFlags`  
 \[in\] 지정은 [LAUNCH\_FLAGS](../../../extensibility/debugger/reference/launch-flags.md) 세션입니다.  
  
 `hStdInput`  
 \[in\] 하는 대체 입력된 스트림을 처리 합니다.  리디렉션이 필요 없는 경우 0 일 수 있습니다.  
  
 `hStdOutput`  
 \[in\] 대체 출력 스트림으로 처리 합니다.  리디렉션이 필요 없는 경우 0 일 수 있습니다.  
  
 `hStdError`  
 \[in\] 대체 오류 출력 스트림으로 처리 합니다.  리디렉션이 필요 없는 경우 0 일 수 있습니다.  
  
 `pCallback`  
 \[in\] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 는 디버거 이벤트를 수신 하는 개체입니다.  
  
 `ppDebugProcess`  
 \[out\] 반환 결과 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 시작된 된 프로세스를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 일반적으로, [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 사용 하 여 프로그램을 시작 합니다를 [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) 메서드 및 다음 일시 중단된 프로그램에 디버거를 연결 합니다.  그러나 가지 환경에서 디버그 엔진 수 있습니다 필요한 경우에 \(예는 인터프리터의 일부 디버그 엔진입니다 및 디버깅 중인 프로그램 언어인 경우\)에서 프로그램을 실행 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 를 사용 하는 `IDebugEngineLaunch2::LaunchSuspended` 메서드.  
  
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md) 메서드를 호출할 프로세스를 일시 중단된 상태에서 성공적으로 실행 된 이후 프로세스를 시작 합니다.  
  
## 참고 항목  
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [LAUNCH\_FLAGS](../../../extensibility/debugger/reference/launch-flags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)   
 [ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)