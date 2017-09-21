---
title: "IDebugEngine2::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngine2::Attach"
helpviewer_keywords: 
  - "IDebugEngine2::Attach"
ms.assetid: 173dcbda-5019-4c5e-bca9-a071838b5739
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# IDebugEngine2::Attach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\) 프로그램 또는 프로그램을 연결합니다.  실행 중인 프로세스에는 SDM은 DE 때 세션 디버그 매니저 \(SDM\) 호출 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT Attach(   
   IDebugProgram2**      pProgram,  
   IDebugProgramNode2**  rgpProgramNodes,  
   DWORD                 celtPrograms,  
   IDebugEventCallback2* pCallback,  
   ATTACH_REASON         dwReason  
);  
```  
  
```c#  
int Attach(   
   IDebugProgram2[]     pProgram,  
   IDebugProgramNode2[] rgpProgramNodes,  
   uint                 celtPrograms,  
   IDebugEventCallback2 pCallback,  
   Enum_ATTACH_REASON   dwReason  
);  
```  
  
#### 매개 변수  
 `pProgram`  
 \[in\] 배열 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 에 연결 하는 프로그램을 나타내는 개체입니다.  이러한 포트는 프로그램입니다.  
  
 `rgpProgramNodes`  
 \[in\] 배열 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 프로그램 노드, 각 프로그램에 대해 하나를 나타내는 개체입니다.  동일한 프로그램에서 프로그램 노드의이 배열에 표현 `pProgram`.  프로그램을 연결 하는 DE 식별할 수 있도록 프로그램 노드가 제공 됩니다.  
  
 `celtPrograms`  
 \[in\] 많은 프로그램 및\/또는 프로그램 노드에서 `pProgram` 및 `rgpProgramNodes` 배열입니다.  
  
 `pCallback`  
 \[in\] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) SDM을 디버그 이벤트를 보내는 데 사용할 수 있는 개체입니다.  
  
 `dwReason`  
 \[in\] 값은 [ATTACH\_REASON](../../../extensibility/debugger/reference/attach-reason.md) 이러한 프로그램 연결에 대 한 이유를 지정 하는 열거형입니다.  자세한 내용은 설명 단원을 참조하십시오.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 다음과 같은 방법으로 응용 프로그램에 연결 하는 세 가지 이유가 있습니다.  
  
-   `ATTACH_REASON_LAUNCH`사용자가 포함 된 프로세스를 시작 하기 때문에 DE 프로그램에 연결 됨을 나타냅니다.  
  
-   `ATTACH_REASON_USER`사용자가 프로그램 또는 프로그램을 포함 하는 프로세스에 연결 하는 DE 명시적으로 요청한 것을 나타냅니다.  
  
-   `ATTACH_REASON_AUTO`다른 프로그램에서 특정 프로세스가 이미 디버깅 하기 때문에 특정 프로그램에는 DE 연결 됨을 나타냅니다.  이 라고도 자동 연결 됩니다.  
  
 이 메서드를 호출 하면 DE은 시퀀스에서이 이벤트를 보낼 필요가 있습니다.  
  
1.  [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)\(아직 없는 경우 디버그 엔진의 특정 인스턴스에 대 한 전송 되었습니다\)  
  
2.  [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
  
3.  [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)  
  
 사유를 첨부 한 경우 뿐만 아니라, `ATTACH_REASON_LAUNCH`, DE는 보내야 할의 [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) 이벤트입니다.  
  
 DE 가져옵니다 한 번은 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 어떤 개인 인터페이스를 쿼리할 수 있습니다 수 개체 디버깅 중인 프로그램에 해당 합니다.  
  
 주어진 배열의 노드 프로그램의 메서드를 호출 하기 전에 `pProgram` 또는 `rgpProgramNodes`, 가장 필요한 경우 활성화에 `IDebugProgram2` 인터페이스가 있는 프로그램을 나타냅니다.  그러나 일반적으로,,이 단계 필요 하지 않습니다.  자세한 내용은 [보안 문제](../../../extensibility/debugger/security-issues.md)를 참조하십시오.  
  
## 참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [ATTACH\_REASON](../../../extensibility/debugger/reference/attach-reason.md)   
 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)   
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)   
 [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)