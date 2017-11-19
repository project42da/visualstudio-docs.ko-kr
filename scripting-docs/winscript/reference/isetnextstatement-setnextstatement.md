---
title: ISetNextStatement::SetNextStatement | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: ISetNextStatement.SetNextStatement
apilocation: scrobj.dll
ms.assetid: c5534f3b-39a5-4466-b8fc-69b717c6eee9
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d21dafcd8cdb762e39f0cfcbde1162dd66c275ec
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="isetnextstatementsetnextstatement"></a>ISetNextStatement::SetNextStatement
이 메서드는 스크립트 해석 실행할 수 있는 다음 코드 컨텍스트를 업데이트 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetNextStatement(  
   IDebugStackFrame*  pStackFrame,  
   IDebugCodeContext*  pCodeContext  
)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStackFrame`  
 [in] 스택 프레임 개체에 대 한 포인터입니다.  
  
 `pCodeContext`  
 [in] 코드 컨텍스트 개체에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [ISetNextStatement 인터페이스](../../winscript/reference/isetnextstatement-interface.md)