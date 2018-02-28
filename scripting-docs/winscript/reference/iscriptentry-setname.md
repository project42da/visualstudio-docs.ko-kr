---
title: IScriptEntry::SetName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IScriptEntry.SetName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetName
ms.assetid: dfa33450-87d7-4c8e-bfd8-0cc2d6542a0e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 43e167ce48c208b6f552984fe2db9ec9d48c72eb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptentrysetname"></a>IScriptEntry::SetName
단일 개체 (예: 함수)를 나타내는 항목에 대 한 개체의 이름을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetName(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `psz`  
 [in] 새 이름을 `IScriptEntry` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptEntry::GetName](../../winscript/reference/iscriptentry-getname.md)