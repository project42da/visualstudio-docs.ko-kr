---
title: IActiveScriptGarbageCollector::CollectGarbage | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 75f77c49-2190-4d49-a3e0-9dcf847c502b
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07d5a00e04939331f85c4c74727aaf03b62814fa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptgarbagecollectorcollectgarbage"></a>IActiveScriptGarbageCollector::CollectGarbage
액티브 스크립트 호스트는 가비지 수집을 시작 하려면이 메서드를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CollectGarbage(        SCRIPTGCTYPE scriptgctype    );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `scriptgctype`  
 [in] [SCRIPTGCTYPE 열거형](../../winscript/reference/scriptgctype-enumeration.md) 정상 또는 exhaustive 가비지 수집 수행 여부를 지정 하 합니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptGarbageCollector 인터페이스](../../winscript/reference/iactivescriptgarbagecollector-interface.md)