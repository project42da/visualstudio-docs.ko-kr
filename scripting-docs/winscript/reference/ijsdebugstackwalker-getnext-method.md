---
title: "Ijsdebugstackwalker:: Getnext 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugStackWalker.GetNext
apilocation: jscript9diag.dll
ms.assetid: 0b124768-50d3-4a69-876c-1aa337839a4e
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 695bb6cecc2a27565dce21b4a965ad08d90d7be7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugstackwalkergetnext-method"></a>IJsDebugStackWalker::GetNext 메서드
다음 프레임을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNext(  
   IJsDebugFrame **ppFrame  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppFrame`  
 [out] 스택 프레임을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 더 이상 스택 프레임이을 열거할 수 있는 경우 E_JsDEBUG_OUTSIDE_OF_VM를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugStackWalker 인터페이스](../../winscript/reference/ijsdebugstackwalker-interface.md)