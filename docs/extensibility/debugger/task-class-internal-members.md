---
title: Task 클래스-내부 멤버 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, Task class [.NET Framework]
- Task class [.NET Framework debug engines]
ms.assetid: 28e47c3b-9323-424a-80ac-6cc3bf19e09b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 161572ece44f3a9f07c9eb40638ca98170e3a86c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="task-class---internal-members"></a>작업 클래스-내부 멤버
이 항목의 내부 멤버를 설명 합니다.는 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 사용자 지정 디버거를 구현 하는 데 도움이 되는 클래스입니다. 이 클래스에 대 한 일반 정보에 대 한 참조는 <xref:System.Threading.Tasks.Task> 참조 항목입니다.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** (mscorlib.dll)에 mscorlib  
  
 .NET Framework에서 이러한 내부 멤버에 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
.class public auto ansi System.Threading.Tasks.Task  
       extends System.Object  
       implements System.Threading.IThreadPoolWorkItem,  
                  System.IAsyncResult,  
                  System.IDisposable,  
                  System.Threading.ICancelableOperation  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|이름|설명|  
|----------|-----------------|  
|[SetNotificationForWaitCompletion 메서드](../../extensibility/debugger/setnotificationforwaitcompletion-method.md)|설정 하거나 TASK_STATE_WAIT_COMPLETION_NOTIFICATION 상태 비트를 지웁니다.|  
|[NotifyDebuggerOfWaitCompletion 메서드](../../extensibility/debugger/notifydebuggerofwaitcompletion-method.md)|디버거가 중단점 대상으로 사용 되는 자리 표시자 메서드.|  
  
### <a name="fields"></a>필드  
  
|이름|설명|  
|----------|-----------------|  
|[m_action](../../extensibility/debugger/m-action-field.md)|실행할 코드를 나타내는 대리자는 <xref:System.Threading.Tasks.Task> 개체입니다.|  
|[m_contingentProperties](../../extensibility/debugger/m-contingentproperties-field.md)|추가 속성을 저장는 <xref:System.Threading.Tasks.Task> 개체입니다.|  
|[m_parent](../../extensibility/debugger/m-parent-field.md)|에 대 한 지원 필드는 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 부모 속성입니다.|  
|[m_stateFlags](../../extensibility/debugger/m-stateflags-field.md)|현재 상태에 대 한 정보를 저장 된 <xref:System.Threading.Tasks.Task> 개체입니다.|  
|[m_stateObject](../../extensibility/debugger/m-stateobject-field.md)|동작에 의해 사용 될 데이터를 표시 하는 개체입니다.|  
|[m_taskId](../../extensibility/debugger/m-taskid-field.md)|에 대 한 지원 필드는 <xref:System.Threading.Tasks.Task.Id%2A?displayProperty=fullName> 속성입니다.|  
|[s_taskIdCounter](../../extensibility/debugger/s-taskidcounter-field.md)|에 대 한 사용 가능한 다음 식별자는 <xref:System.Threading.Tasks.Task> 개체입니다.|  
|[TASK_STATE_CANCELED](../../extensibility/debugger/task-state-canceled-field.md)|실행 중 상태에 도달 하기 전에 작업이 취소 된 코드 또는 작업의 취소를 승인 했습니다 예외 없이 완료를 나타냅니다.|  
|[TASK_STATE_EXECUTED](../../extensibility/debugger/task-state-executed-field.md)|작업이 실행 되 고 있는지를 나타냅니다.|  
|[TASK_STATE_FAULTED](../../extensibility/debugger/task-state-faulted-field.md)|처리 되지 않은 예외로 인해 작업이 완료 되었음을 나타냅니다.|  
|[TASK_STATE_RAN_TO_COMPLETION](../../extensibility/debugger/task-state-ran-to-completion-field.md)|작업 실행을 성공적으로 완료 되었음을 나타냅니다.|  
|[TASK_STATE_WAITING_ON_CHILDREN](../../extensibility/debugger/task-state-waiting-on-children-field.md)|작업 대리자를 실행을 마친 암시적으로 연결 된 자식 작업이 완료 되기를 기다리고 있음을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 다음 내부 메서드는 입구 표시 때문에 디버거 엔진에 유용 <xref:System.Threading.Tasks.Task> 코드 실행:  
  
-   `Execute`  
  
-   `ExecuteEntry`  
  
-   `ExecuteWithThreadLocal`  
  
-   `Finish`  
  
-   `InnerInvoke`  
  
-   `InternalWait`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 [.NET Framework에 대한 병렬 확장 기능 내부](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)