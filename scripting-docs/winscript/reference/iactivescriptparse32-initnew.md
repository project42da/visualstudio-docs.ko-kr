---
title: IActiveScriptParse32::InitNew | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c77aa16-f391-4c93-9f1a-4e529a9930b2
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 31de8258ae13855741c6dd5ca9e4ff2c589e97bf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptparse32initnew"></a>IActiveScriptParse32::InitNew
스크립팅 엔진을 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT InitNew(void);  
```  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 하면 또는 `E_FAIL` 초기화 하는 동안 오류가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 스크립팅 엔진을 사용할 수 있습니다, 전에 다음 방법 중 하나를 호출 해야: `IPersist*::Load`, `IPersist*::InitNew`, 또는 `IActiveScriptParse32::InitNew`합니다. 이 메서드의 의미론이 `IPersistStreamInit::InitNew`에이 메서드를 초기화할 스크립팅 엔진에 지시 합니다. 둘 다를 호출할 수는 `IPersist*::InitNew` 또는 `IActiveScriptParse32::InitNew` 및 `IPersist*::Load`를 호출할 수는 `IPersist*::InitNew`, `IActiveScriptParse32::InitNew`, 또는 `IPersist*::Load` 두 번 이상.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptParse32](../../winscript/reference/iactivescriptparse32.md)