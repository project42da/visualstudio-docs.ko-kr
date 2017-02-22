---
title: "IDebugProgram2::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgram2::Attach"
helpviewer_keywords: 
  - "IDebugProgram2::Attach"
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgram2::Attach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램에 첨부합니다.  
  
## 구문  
  
```cpp#  
HRESULT Attach(   
   IDebugEventCallback2* pCallback  
);  
```  
  
```c#  
int Attach(   
   IDebugEventCallback2 pCallback  
);  
```  
  
#### 매개 변수  
 `pCallback`  
 \[in\] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 개체에 대 한 디버그 이벤트 알림을 사용할 수 있습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  몇 가지 가능한 오류 코드는 다음과 같습니다.  
  
|값|설명|  
|-------|--------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|지정 된 프로그램에 디버거가 이미 연결 되어 있습니다.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|보안 위반이 연결 과정 동안 발생 했습니다.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|데스크탑 프로그램을 디버거에 연결할 수 없습니다.|  
  
## 설명  
 디버그 엔진 \(DE\) 프로그램에 연결 하려면이 메서드를 호출 하지 않습니다.  DE는 프로그램의 주소 공간에서 실행 되는 경우는 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드가 호출 됩니다.  DE 연속 \(SDM\) 세션 디버그 관리자의 주소 공간을 경우는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드가 호출 됩니다.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)