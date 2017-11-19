---
title: IDebugApplication::StepOutComplete | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugApplication.StepOutComplete
apilocation: pdm.dll
helpviewer_keywords: IDebugApplication::StepOutComplete
ms.assetid: 9675b214-7be5-4cf7-a63f-7865f3c54371
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c344f0316bda6ed5ef895c1b88ae7b1a6465e73
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationstepoutcomplete"></a>IDebugApplication::StepOutComplete
호출자에 게 반환 단일 단계 모드에서 언어 엔진 임을 프로세스 디버그 관리자에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StepOutComplete();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수가 없습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 가 호출자에 게 반환 되기 바로 전에 단일 단계 모드에서이 메서드를 호출 하는 언어 엔진. 디버그 프로세스 관리자는 첫 번째 기회에 중단 해야 하는 다른 모든 스크립트 엔진에 알리기 위해이 기회를 사용 합니다. 이 방법은 모드의 구현 방법을 언어 간 호환성 단계에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)