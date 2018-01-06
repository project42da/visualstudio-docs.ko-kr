---
title: IDebugEngineLaunch2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngineLaunch2
helpviewer_keywords: IDebugEngineLaunch2 interface
ms.assetid: 5eaf2ad8-3fbf-446e-b48b-5327ad3f5255
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fb53f64b6b98ed6d02774977138cfd4faf5b8f83
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugenginelaunch2"></a>IDebugEngineLaunch2
디버그 엔진 (DE)에서 실행 되 고 프로그램을 종료 하는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugEngineLaunch2 : IDebugEngine2  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스는 사용자 지정 포트에서 모두 처리할 수 없는 프로세스를 시작 하기 위한 특별 한 요구 사항이 있는 경우 사용자 지정 DE 하 여 구현 됩니다. 이 일반적으로 대/소문자는 DE 해석기의 일부인 경우 디버깅 중인 프로세스는 스크립트: 인터프리터를 먼저 시작 해야 하 고 스크립트가 로드 되 고 시작 합니다. 포트 인터프리터를 시작할 수 있지만 스크립트 (여기서는 DE는 역할을이) 특수 한 처리가 필요할 수 있습니다. 이 인터페이스는 사용자 지정 포트를 처리할 수 없는 프로그램을 시작 하는 것에 대 한 고유한 요구 사항이 있는 경우에 구현 됩니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스는 세션 디버그 관리자 (SDM)은 SDM이이 인터페이스를 가져올 수 있는 경우에서 호출 된 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 인터페이스 (QueryInterface 사용). 이 인터페이스를 가져올 경우는 DE 특별 한 요구 사항이 있으며 응용 프로그램을 시작 하는 포트 대신 프로그램을 시작 하려면이 인터페이스를 호출 하는 SDM 알고 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugEngineLaunch2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)|DE를 사용 하 여 프로세스를 시작합니다.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)|이력서 처리 실행 합니다.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md)|프로세스를 종료할 수 하는 경우를 결정 합니다.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)|프로세스를 종료 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)