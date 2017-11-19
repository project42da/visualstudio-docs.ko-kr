---
title: IScriptNode::GetChild | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IScriptNode.GetChild
apilocation: scrobj.dll
helpviewer_keywords: IScriptNode::GetChild
ms.assetid: 8cb3f8b0-958b-40bb-a91a-49a788661861
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d127b1b8a8db0c6d272e50d33b523fbe182a9e21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptnodegetchild"></a>IScriptNode::GetChild
노드에 지정 된 인덱스에 있는 자식 항목을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetChild(  
   ULONG              isn,  
   IScriptNode        **ppsn  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `isn`  
 [in] 부모에서 자식 요소의 인덱스입니다.  
  
 `ppsn`  
 [out] 에 대 한 포인터를 수신 하는 변수의 주소는 `IScriptNode` 자식 인스턴스는 인터페이스입니다.  
  
 에 대 한 `IScriptNode` 웹 페이지를 나타내는 개체를이 매개 변수는 스크립트 블록을 포함 하는 개체를 반환 합니다.  
  
 에 대 한 `IScriptEntry` 스크립트 블록을 지정 하는 개체,이 매개 변수는 함수를 지정 하는 개체를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 에 대 한 `IScriptEntry` 함수 개체를 지정 하는 개체에 대 한 및 `IScriptScriptlet` 개체의 경우이 메서드는 자식 항목이 없는 있기 때문에 실패 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)