---
title: "IJsDebugFrame 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5af46b18-9d25-4a23-b8d1-fa23bea3efcf
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f09a147375661fb52b88f531aff981897138adff
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugframe-interface"></a>IJsDebugFrame 인터페이스
스택 프레임을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IJsDebugFrame : public IUnknown;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IJsDebugFrame::Evaluate 메서드](../../winscript/reference/ijsdebugframe-evaluate-method.md)|이 스택 프레임의 컨텍스트에서 식을 평가 합니다.|  
|[IJsDebugFrame::GetDebugProperty 메서드](../../winscript/reference/ijsdebugframe-getdebugproperty-method.md)|이 스택 프레임에 대 한 속성 브라우저를 반환합니다.|  
|[IJsDebugFrame::GetDocumentPositionWithId 메서드](../../winscript/reference/ijsdebugframe-getdocumentpositionwithid-method.md)|사용자 수준 문서 내에서이 스택 프레임의 현재 위치를 반환합니다.|  
|[IJsDebugFrame::GetDocumentPositionWithName 메서드](../../winscript/reference/ijsdebugframe-getdocumentpositionwithname-method.md)|사용자 수준 문서 내에서이 스택 프레임의 현재 위치를 반환합니다.|  
|[IJsDebugFrame::GetName 메서드](../../winscript/reference/ijsdebugframe-getname-method.md)|스택 프레임의 이름을 가져옵니다.|  
|[IJsDebugFrame::GetReturnAddress 메서드](../../winscript/reference/ijsdebugframe-getreturnaddress-method.md)|'시작'에 푸시되 반환 주소를 가져옵니다 (GetStackRange 참조) 프레임의 합니다.|  
|[IJsDebugFrame::GetStackRange 메서드](../../winscript/reference/ijsdebugframe-getstackrange-method.md)|논리 JavaScript 스택 프레임의 절대 주소 범위를 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)