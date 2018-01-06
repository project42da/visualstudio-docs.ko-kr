---
title: IDebugProgram2::Execute | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgram2::Execute
helpviewer_keywords: IDebugProgram2::Execute
ms.assetid: f7205ce8-0ac6-4fcd-b6ec-b720b4fcaccf
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2e53f13aea93de8f39c5802dd2a12598ad938f64
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2execute"></a>IDebugProgram2::Execute
중지 된 상태에서이 프로그램을 실행을 계속 합니다. 이전 실행 상태 (예: 단계)의 선택을 취소 하면, 프로그램 실행을 다시 시작 합니다.  
  
> [!NOTE]
>  이 메서드는 사용 되지 않습니다. 사용 하 여 [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Execute(  
   void  
);  
```  
  
```csharp  
int Execute();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 다른 프로그램의 스레드 중지 된 상태에서 실행을 시작할 때이 메서드는이 프로그램에 호출 됩니다. 이 메서드는 사용자가을 선택할 때에 호출 됩니다는 **시작** 명령을 **디버그** IDE의 메뉴. 이 메서드의 구현을 호출 처럼 간단 해질 수 있습니다는 [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md) 프로그램에서 현재 스레드의 메서드.  
  
> [!WARNING]
>  Stopping 이벤트 또는 즉시 (동기) 이벤트를 보내지 않음 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출을 처리 하는 동안 그렇지 않은 경우 디버거가 중단 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)