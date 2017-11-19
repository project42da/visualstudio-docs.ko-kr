---
title: "IJsDebugProcess 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a7ad5525-55b7-4c68-a4f7-c508f7877712
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f2a81104f51ca1a66c493779146b7eaa102ea300
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugprocess-interface"></a>IJsDebugProcess 인터페이스
검사 하 고 대상 프로세스 제어 루틴을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IJsDebugProcess : public IUnknown;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IJsDebugProcess::CreateBreakPoint 메서드](../../winscript/reference/ijsdebugprocess-createbreakpoint-method.md)|지정한 문서 위치에서 중단점을 설정합니다.|  
|[IJsDebugProcess::CreateStackWalker 메서드](../../winscript/reference/ijsdebugprocess-createstackwalker-method.md)|스택 워크에 대 한 팩터리 메서드입니다.|  
|[IJsDebugProcess::PerformAsyncBreak 메서드](../../winscript/reference/ijsdebugprocess-performasyncbreak-method.md)|다음 스크립트 명령에서 중단 하도록 프로그램이 중단 모드에서 스크립트 엔진을 넣습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)