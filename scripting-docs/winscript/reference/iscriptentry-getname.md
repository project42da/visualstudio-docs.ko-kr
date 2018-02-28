---
title: IScriptEntry::GetName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IScriptEntry.GetName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetName
ms.assetid: 56daa288-618f-497c-a360-7d443afd478b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fc518e87414d051e9b1393b60b5874a0204b78b2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptentrygetname"></a>IScriptEntry::GetName
단일 개체 (예: 함수)를 나타내는 항목에 대 한 개체의 이름을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetName(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstr`  
 [out] 가 나타내는 개체의 이름에서 `IScriptEntry` 스크립트 블록입니다. 항목에서 단일 개체를 나타낼 경우에 NULL이 반환 됩니다.  
  
 자식 항목에는 단일 함수 개체를 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptNode:: CreateChildEntry](../../winscript/reference/iscriptnode-createchildentry.md)