---
title: IActiveScriptAuthor::GetRoot | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptAuthor.GetRoot
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptAuthor::GetRoot
ms.assetid: 8e55a0c0-dd35-43d5-bf6f-e2f59c1e88d1
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bb20a896d54c2b8e85c93014e6bd8ad3c906f55c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthorgetroot"></a>IActiveScriptAuthor::GetRoot
반환 된 `IScriptNode` 저자의 스크립트 트리의 루트입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRoot(  
   IScriptNode        **ppsp  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppsp`  
 [out] 에 대 한 포인터를 수신 하는 변수의 주소는 `IScriptNode` 루트 노드는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)