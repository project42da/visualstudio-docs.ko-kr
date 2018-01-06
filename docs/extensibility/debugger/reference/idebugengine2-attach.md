---
title: IDebugEngine2::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine2::Attach
helpviewer_keywords: IDebugEngine2::Attach
ms.assetid: 173dcbda-5019-4c5e-bca9-a071838b5739
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fb45d2196a9f84b8f956b8ede665df6e3ed249c2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengine2attach"></a>IDebugEngine2::Attach
프로그램 또는 프로그램을 디버그 엔진 (DE)를 연결합니다. DE는 프로세스 내에서 실행 하 여 SDM 세션 디버그 관리자 (SDM)에서 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Attach(   
   IDebugProgram2**      pProgram,  
   IDebugProgramNode2**  rgpProgramNodes,  
   DWORD                 celtPrograms,  
   IDebugEventCallback2* pCallback,  
   ATTACH_REASON         dwReason  
);  
```  
  
```csharp  
int Attach(   
   IDebugProgram2[]     pProgram,  
   IDebugProgramNode2[] rgpProgramNodes,  
   uint                 celtPrograms,  
   IDebugEventCallback2 pCallback,  
   Enum_ATTACH_REASON   dwReason  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pProgram`  
 [in] 배열을 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 프로그램에 연결을 나타내는 개체입니다. 이들은 포트 프로그램입니다.  
  
 `rgpProgramNodes`  
 [in] 배열을 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 각 프로그램에 대 한 프로그램 노드를 나타내는 개체입니다. 이 배열에 있는 프로그램 노드가 표현에서 같이 동일한 프로그램 `pProgram`합니다. 프로그램 노드는 DE 연결할 프로그램을 식별할 수 있도록 제공 됩니다.  
  
 `celtPrograms`  
 [in] 프로그램 및/또는 프로그램에는 노드 개수는 `pProgram` 및 `rgpProgramNodes` 배열입니다.  
  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 은 SDM에 디버그 이벤트를 보내는 데 사용할 개체입니다.  
  
 `dwReason`  
 [in] 값은 [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) 이러한 프로그램을 연결 하기 위한 이유를 지정 하는 열거형입니다. 자세한 내용은 설명 섹션을 참조하세요.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 다음과 같이 프로그램에 연결 하기 위한 세 가지 이유가 있습니다.  
  
-   `ATTACH_REASON_LAUNCH`사용자는 포함 하는 프로세스를 시작 하기 때문에 프로그램에는 DE이 연결을 나타냅니다.  
  
-   `ATTACH_REASON_USER`사용자가 프로그램 (또는 프로그램을 포함 하는 프로세스)에 연결 하려면 DE 요청 명시적으로 나타냅니다.  
  
-   `ATTACH_REASON_AUTO`DE이 다른 프로그램에서 특정 프로세스를 디버깅 하는 이미 때문에 특정 프로그램에 연결 됨을 나타냅니다. 가 자동으로 연결 합니다.  
  
 이 메서드를 호출할 때는 DE 시퀀스에서 이러한 이벤트를 전송 해야 합니다.  
  
1.  [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md) (하는 경우이 전송 되지 않은 이미 디버그 엔진의 특정 인스턴스에 대해)  
  
2.  [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
  
3.  [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)  
  
 또한 연결에 대 한 설명이 `ATTACH_REASON_LAUNCH`를 전송 해야 하는 DE는 [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) 이벤트입니다.  
  
 한 번 DE 가져옵니다는 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 개체 디버깅 중인 프로그램에 해당 개인 인터페이스에 대해 쿼리할 수 있습니다.  
  
 제공한 배열에서 프로그램 노드의 메서드를 호출 하기 전에 `pProgram` 또는 `rgpProgramNodes`, 가장을 사용 하면 필요한 경우에서 사용할 수 있어야는 `IDebugProgram2` 프로그램 노드를 나타내는 인터페이스입니다. 일반적으로 이때이 단계가 필요 하지 않습니다. 자세한 내용은 참조 [보안 문제](../../../extensibility/debugger/security-issues.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)   
 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)   
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)   
 [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)