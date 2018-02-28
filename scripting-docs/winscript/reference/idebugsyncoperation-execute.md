---
title: IDebugSyncOperation::Execute | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugSyncOperation.Execute
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugSyncOperation::Execute
ms.assetid: a45b8c7d-c51a-4098-877f-fbec2f1f6947
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 69e07c646bfa176f5e2dc07539f301a8ef5c5273
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugsyncoperationexecute"></a>IDebugSyncOperation::Execute
동기적으로 작업을 수행 하 고 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Execute(  
   IUnknown**  ppunkResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppunkResult`  
 [out] 작업에서 반환 되는 개체 매개 변수.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_ABORT`|호출 하 여 작업이 중단 되었습니다는 `IDebugSyncOperation::InProgressAbort` 메서드.|  
  
## <a name="remarks"></a>설명  
 대상 스레드 호출에서 프로세스를 디버깅 관리자는 `Execute` 메서드 동기적으로 처리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSyncOperation 인터페이스](../../winscript/reference/idebugsyncoperation-interface.md)