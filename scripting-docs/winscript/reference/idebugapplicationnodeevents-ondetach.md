---
title: IDebugApplicationNodeEvents::onDetach | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugApplicationNodeEvents.onDetach
apilocation: scrobj.dll
helpviewer_keywords: IDebugApplicationNodeEvents::onDetach
ms.assetid: ef0cbe40-8c52-4bc9-bed0-9fc508abec6e
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b5f1ccc35e83f4fa016b5ff3dae8fac867bb8d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationnodeeventsondetach"></a>IDebugApplicationNodeEvents::onDetach
디버그 응용 프로그램 노드 개체 부모 노드에서 분리 된 이름임을 하는 이벤트를 처리 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT onDetach();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수가 없습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버그 응용 프로그램 노드 개체 부모 노드에서 분리 된 이름임을 하는 이벤트를 처리 합니다.  
  
 구현자는 `IDebugApplicationNode` 인터페이스에는이 이벤트가 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationNodeEvents 인터페이스](../../winscript/reference/idebugapplicationnodeevents-interface.md)   
 [IDebugApplicationNodeEvents::onAttach](../../winscript/reference/idebugapplicationnodeevents-onattach.md)   
 [IDebugApplicationNode 인터페이스](../../winscript/reference/idebugapplicationnode-interface.md)