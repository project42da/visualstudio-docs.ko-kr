---
title: IScriptEntry::GetBody | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IScriptEntry.GetBody
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetBody
ms.assetid: 419c8c11-a1f8-4b97-ab00-e8af2b2f9bfc
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9daa04009cf7088cbd21a2d3dfa185f581c157a3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptentrygetbody"></a>IScriptEntry::GetBody
본문에 해당 하는 텍스트를 반환 합니다.는 `IScriptEntry` 스크립트 블록, 함수 블록 또는 스크립틀릿 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetBody(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstr`  
 [out] 다음 중 하나의 본문에 있는 텍스트:  
  
-   `IScriptEntry` 스크립트 블록  
  
-   `IScriptEntry` 함수 블록의 함수  
  
-   `IScriptEntry` 스크립틀릿 이벤트 처리기  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)