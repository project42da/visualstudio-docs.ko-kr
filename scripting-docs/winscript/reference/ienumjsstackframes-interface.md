---
title: "IEnumJsStackFrames 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 49e7b425-df17-4d7f-87ff-0bc82715c911
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 12583f73c9f3977371ebd193716f2513fc0befc4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ienumjsstackframes-interface"></a>IEnumJsStackFrames 인터페이스
스택을 제공 하도록 디버거를 구현한 JavaScript 위한 jscript9diag.dll를 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEnumJsStackFrames : public IUnknown;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IEnumJsStackFrames::Next 메서드](../../winscript/reference/ienumjsstackframes-next-method.md)|지정 된 프레임 수를 가져옵니다.|  
|[IEnumJsStackFrames::Reset 메서드](../../winscript/reference/ienumjsstackframes-reset-method.md)|첫 번째 요소 앞으로 스택 프레임을 다시 설정합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)