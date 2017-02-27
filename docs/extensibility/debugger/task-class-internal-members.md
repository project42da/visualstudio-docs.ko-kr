---
title: "작업 클래스-내부 멤버 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버그 엔진, 작업 클래스 [.NET Framework]"
  - "작업 클래스 [.NET Framework 디버그 엔진]"
ms.assetid: 28e47c3b-9323-424a-80ac-6cc3bf19e09b
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 작업 클래스-내부 멤버
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 항목의 내부 멤버를 설명 합니다.는 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 사용자 지정 디버거를 구현 하는 데 도움이 되는 클래스입니다. 이 클래스에 대 한 일반 정보에 대 한 참조는 <xref:System.Threading.Tasks.Task> 참조 항목입니다.  
  
 **네임 스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** \(mscorlib.dll\)에 mscorlib  
  
 .NET Framework에서 이러한 내부 멤버를 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 \(CIL\) 제공 됩니다.  
  
## 구문  
  
```  
.class public auto ansi System.Threading.Tasks.Task  
       extends System.Object  
       implements System.Threading.IThreadPoolWorkItem,  
                  System.IAsyncResult,  
                  System.IDisposable,  
                  System.Threading.ICancelableOperation  
```  
  
## 멤버  
  
### 메서드  
  
|이름|설명|  
|--------|--------|  
|[SetNotificationForWaitCompletion 메서드](../../extensibility/debugger/setnotificationforwaitcompletion-method.md)|설정 하거나 TASK\_STATE\_WAIT\_COMPLETION\_NOTIFICATION 상태 비트를 해제 합니다.|  
|[NotifyDebuggerOfWaitCompletion 메서드](../../extensibility/debugger/notifydebuggerofwaitcompletion-method.md)|디버거에서 중단점 대상으로 사용 하는 자리 표시자 방법입니다.|  
  
### 필드  
  
|이름|설명|  
|--------|--------|  
|[m\_action](../../extensibility/debugger/m-action-field.md)|실행 하는 코드를 나타내는 대리자는 <xref:System.Threading.Tasks.Task> 개체입니다.|  
|[m\_contingentProperties](../../extensibility/debugger/m-contingentproperties-field.md)|추가 속성을 저장 된 <xref:System.Threading.Tasks.Task> 개체입니다.|  
|[m\_parent](../../extensibility/debugger/m-parent-field.md)|에 대 한 지원 필드는 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 부모 속성입니다.|  
|[m\_stateFlags](../../extensibility/debugger/m-stateflags-field.md)|현재 상태에 대 한 정보를 저장 된 <xref:System.Threading.Tasks.Task> 개체입니다.|  
|[m\_stateObject](../../extensibility/debugger/m-stateobject-field.md)|동작에 의해 사용 될 데이터를 나타내는 개체입니다.|  
|[m\_taskId](../../extensibility/debugger/m-taskid-field.md)|에 대 한 지원 필드는 <xref:System.Threading.Tasks.Task.Id%2A?displayProperty=fullName> 속성입니다.|  
|[s\_taskIdCounter](../../extensibility/debugger/s-taskidcounter-field.md)|에 대 한 사용 가능한 다음 식별자는 <xref:System.Threading.Tasks.Task> 개체입니다.|  
|[TASK\_STATE\_CANCELED](../../extensibility/debugger/task-state-canceled-field.md)|실행 상태에 도달 하기 전에 작업이 취소 되었는지 또는 작업의 취소를 승인 하 고 예외 없이 완료를 나타냅니다.|  
|[TASK\_STATE\_EXECUTED](../../extensibility/debugger/task-state-executed-field.md)|작업이 실행 중임을 나타냅니다.|  
|[TASK\_STATE\_FAULTED](../../extensibility/debugger/task-state-faulted-field.md)|처리 되지 않은 예외로 인해 작업이 완료 되었음을 나타냅니다.|  
|[TASK\_STATE\_RAN\_TO\_COMPLETION](../../extensibility/debugger/task-state-ran-to-completion-field.md)|작업 실행을 성공적으로 완료 되었음을 나타냅니다.|  
|[TASK\_STATE\_WAITING\_ON\_CHILDREN](../../extensibility/debugger/task-state-waiting-on-children-field.md)|작업 대리자를 실행이 완료 되 고 암시적으로 연결 된 자식 작업 완료 대기 중 나타냅니다.|  
  
## 설명  
 입구를 표시 하기 때문에 내부 메서드는 디버거 엔진에 유용한 <xref:System.Threading.Tasks.Task> 코드 실행 합니다.  
  
-   `Execute`  
  
-   `ExecuteEntry`  
  
-   `ExecuteWithThreadLocal`  
  
-   `Finish`  
  
-   `InnerInvoke`  
  
-   `InternalWait`  
  
## 참고 항목  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 [.NET Framework에 대 한 병렬 확장 기능의 내부](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)