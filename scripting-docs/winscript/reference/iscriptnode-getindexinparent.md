---
title: IScriptNode::GetIndexInParent | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IScriptNode.GetIndexInParent
apilocation: scrobj.dll
helpviewer_keywords: IScriptNode::GetIndexInParent
ms.assetid: 521c1ca1-2d27-4344-bf3b-d8b53132b648
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3862a48ff4649f018eec79bf0411f23bc9f6d7bd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptnodegetindexinparent"></a>IScriptNode::GetIndexInParent
부모의 자식 목록에 있는 개체의 인덱스를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetIndexInParent(  
   ULONG              pisn,  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pisn`  
 [out] 부모의 자식 목록에 있는 개체의 인덱스를 반환합니다.  
  
 이 메서드는 경우는 `IScriptNode` 개체는 웹 페이지를 나타내는,이 매개 변수 0을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)