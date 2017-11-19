---
title: "Ijsdebugframe:: Getstackrange 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugFrame.GetStackRange
apilocation: jscript9diag.dll
ms.assetid: a6d1d8be-efc0-442d-9756-1959c8f102bd
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cce4d4542f4f76657475636ad6d8e430e1909181
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugframegetstackrange-method"></a>IJsDebugFrame::GetStackRange 메서드
논리 JavaScript 스택 프레임의 절대 주소 범위를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStackRange(  
   UINT64 *pStart,  
   UINT64 *pEnd  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStart`  
 [out] 프레임의 대부분 스택 포인터를 아래로 합니다.  
  
 `pEnd`  
 [out] 상위 대부분 스태커 프레임의 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 이 메서드는 정보를 결합 인터리브 스택 추적 여러 런타임에서 수집 하는 데 유용 합니다. 시작, 끝 스택 포인터에는 여러 물리적 컴퓨터 스택 프레임 (프레임에 대 한 해석 된 JavaScript 런타임) 포함 될 수 있습니다. 시작 >까지 확장 되면서 스택의 높음 낮은 주소를 종료 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugFrame 인터페이스](../../winscript/reference/ijsdebugframe-interface.md)