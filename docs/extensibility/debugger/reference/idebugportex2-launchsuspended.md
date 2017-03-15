---
title: "IDebugPortEx2::LaunchSuspended | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortEx2::LaunchSuspended"
helpviewer_keywords: 
  - "IDebugPortEx2::LaunchSuspended"
ms.assetid: 34b2cf99-2e52-4757-8969-1d12ac517ec0
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPortEx2::LaunchSuspended
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

실행 파일을 시작합니다.  
  
## 구문  
  
```cpp#  
HRESULT LaunchSuspended(   
   LPCOLESTR        pszExe,  
   LPCOLESTR        pszArgs,  
   LPCOLESTR        pszDir,  
   BSTR             bstrEnv,  
   DWORD            hStdInput,  
   DWORD            hStdOutput,  
   DWORD            hStdError,  
   IDebugProcess2** ppPortProcess  
);  
```  
  
```c#  
int LaunchSuspended(   
   string             pszExe,  
   string             pszArgs,  
   string             pszDir,  
   string             bstrEnv,  
   uint               hStdInput,  
   uint               hStdOutput,  
   uint               hStdError,  
   out IDebugProcess2 ppPortProcess  
);  
```  
  
#### 매개 변수  
 `pszExe`  
 \[in\] 실행 될 실행 파일의 이름입니다.  이 전체 경로 또는 상대를 작업 디렉터리에 지정 된 수의 `pszDir` 매개 변수.  
  
 `pszArgs`  
 \[in\] 실행 파일에 전달할 인수입니다.  인수가 없으면 null 값을 수 있습니다.  
  
 `pszDir`  
 \[in\] 실행 파일에서 사용 되는 작업 디렉터리의 이름입니다.  필요한 작업 디렉터리가 없는 경우 null 값을 수 있습니다.  
  
 `bstrEnv`  
 \[in\] 환경 블록의 null로 끝나는 문자열 뒤에 추가 NULL 종결자가 있습니다.  
  
 `hStdInput`  
 \[in\] 하는 대체 입력된 스트림을 처리 합니다.  리디렉션이 필요 없는 경우 0 일 수 있습니다.  
  
 `hStdOutput`  
 \[in\] 대체 출력 스트림으로 처리 합니다.  리디렉션이 필요 없는 경우 0 일 수 있습니다.  
  
 `hStdError`  
 \[in\] 대체 오류 출력 스트림으로 처리 합니다.  리디렉션이 필요 없는 경우 0 일 수 있습니다.  
  
 `ppPortProcess`  
 \[out\] 반환 된 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 시작된 된 프로세스를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는이 일시 중단 되므로 프로세스 및 코드를 실행 실행 됩니다.  [ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md) 메서드를 호출할 프로세스를 다시 시작 합니다.  
  
 디버그 엔진을 또한 프로그램을 시작할 수 있습니다.  자세한 내용은 [프로그램 실행](../../../extensibility/debugger/launching-a-program.md)를 참조하십시오.  
  
## 참고 항목  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)   
 [프로그램 실행](../../../extensibility/debugger/launching-a-program.md)