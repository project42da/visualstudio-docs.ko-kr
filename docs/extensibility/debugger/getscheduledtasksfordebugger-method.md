---
title: GetScheduledTasksForDebugger 메서드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
caps.latest.revision: 10
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1c27bd57684fc0a4de0bf56bcc8db9a5561f7d1f
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger 메서드
모든 예약 된 작업의 배열을 검색합니다.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** (mscorlib.dll)에 mscorlib  
  
 .NET Framework에서이 내부 멤버에 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed  
```  
  
## <a name="return-value"></a>반환 값  
 모든 예약 된 작업의 배열입니다. 각 작업 실행 되거나 실행을 완료 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 스레드로부터 안전 하지 및의 다른 인스턴스에 동시에 사용할 수 없습니다 <xref:System.Threading.Tasks.TaskScheduler> 디버거가 모든 다른 스레드가 일시 중단 하는 경우에 디버거를 호출 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [TaskScheduler 클래스](../../extensibility/debugger/taskscheduler-class-internal-members.md)