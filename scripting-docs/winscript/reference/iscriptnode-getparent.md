---
title: IScriptNode::GetParent | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IScriptNode.GetParent
apilocation: scrobj.dll
helpviewer_keywords: IScriptNode::GetParent
ms.assetid: 0fb813f6-ab94-46b2-b0cf-ef5d1cd38ae4
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1da2f68de40a66b98b97ab7c7eb1d63748f1e07a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptnodegetparent"></a>IScriptNode::GetParent
반환 된 `IScriptNode` 개체의 부모인 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetParent(  
   IScriptNode       **ppsnParent  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppsnParent`  
 [out] 에 대 한 포인터를 수신 하는 변수의 주소는 `IScriptNode` 부모 인스턴스의 인터페이스입니다.  
  
 클래스를 구현 하는 경우 `IScriptEntry` 또는 `IScriptScriptlet`, `IScriptNode` 개체가 반환 됩니다.  
  
 클래스를 구현 하는 경우 `IScriptNode` (웹 페이지를 나타냄), NULL이 반환 됩니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)