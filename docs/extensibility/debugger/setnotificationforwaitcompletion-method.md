---
title: SetNotificationForWaitCompletion 메서드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- SetNotificationForWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: da149c9a-20f4-4543-a29e-429c8c1d2e19
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a005ee7d624604dd716042bd839b48b7a367dd48
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="setnotificationforwaitcompletion-method"></a>SetNotificationForWaitCompletion 메서드
설정 하거나 TASK_STATE_WAIT_COMPLETION_NOTIFICATION 상태 비트를 지웁니다.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** (mscorlib.dll)에 mscorlib  
  
## <a name="syntax"></a>구문  
  
```vb  
internal void SetNotificationForWaitCompletion(bool enabled)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `enabled`  
  
 `true` 비트; 설정 하려면 `false` 에 설정 되지 않은 비트입니다.  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
 디버거는 비동기 메서드 본문 밖으로 단계 수 있도록이 비트를 설정 합니다. 경우 `enabled` 은 `true`, 아직 완료 되지 않은 작업에 대해서만이 메서드를 호출 해야 합니다. 경우 `enabled` 은 `false`, 완료 된 작업에이 메서드를 호출할 수 있습니다. 하거나 이벤트에 프로 미스 스타일 작업에 대 한 사용만 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
## <a name="see-also"></a>참고 항목  
 [작업 클래스](../../extensibility/debugger/task-class-internal-members.md)