---
title: IActiveScriptAuthor::RemoveNamedItem | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptAuthor.RemoveNamedItem
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::RemoveNamedItem
ms.assetid: 1173ef46-39a5-4bc1-8e0c-89259a16be16
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0f3acc7d61d63ce4fb4fe53729ce43324b9718a8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthorremovenameditem"></a>IActiveScriptAuthor::RemoveNamedItem
제거는 `NamedItem` 엔진을 제작 하는 스크립트의 네임 스페이스에서 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemoveNamedItem(  
   LPCOLESTR          pszName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszName`  
 [in] 식별 하는 버퍼의 주소는 `NamedItem` 제거할 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`S_FALSE`|`NamedItem` 개체 엔진을 제작 하는 스크립트의 네임 스페이스에 나타나지 않습니다.|  
  
## <a name="remarks"></a>설명  
 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 를 삽입 하는 데 사용 되는 `NamedItem` 엔진의 네임 스페이스를 제작 하는 스크립트에는 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::AddNamedItem](../../winscript/reference/iactivescriptauthor-addnameditem.md)