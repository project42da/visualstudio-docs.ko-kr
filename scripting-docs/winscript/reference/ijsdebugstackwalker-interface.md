---
title: "IJsDebugStackWalker 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3fe30394-49c8-48e9-bde9-ffe5d79b2121
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dbea11bf1188d148818ea8a082bceec76c704c2b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugstackwalker-interface"></a>IJsDebugStackWalker 인터페이스
지정 된 스레드의 스택 워크를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IJsDebugStackWalker : public IUnknown;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IJsDebugStackWalker::GetNext 메서드](../../winscript/reference/ijsdebugstackwalker-getnext-method.md)|다음 프레임을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 스택 walkers 대상 중지 되 고 대상 프로세스를 다시 계속 되 면 잘못 된 동안에 만들 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)