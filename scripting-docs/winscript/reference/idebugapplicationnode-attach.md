---
title: IDebugApplicationNode::Attach | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugApplicationNode.Attach
apilocation: pdm.dll
helpviewer_keywords: IDebugApplicationNode::Attach
ms.assetid: f4aad4ae-5bb0-4b5e-8f70-912a677f8f7a
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 393186330979d464fe54bde339806a5d8335a859
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationnodeattach"></a>IDebugApplicationNode::Attach
지정 된 프로젝트 트리를이 응용 프로그램 노드를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Attach(  
   IDebugApplicationNode*  pdanParent  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdanParent`  
 [in] 여기서이 응용 프로그램 노드를 추가 해야 하는 프로젝트 트리 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 프로젝트에이 응용 프로그램 노드를 추가 합니다. 트리를 사용 하 여 `pdanParent` 부모로 합니다. 경우 `pdanParent` 은 `NULL`, 최상위 노드로 사용할이 응용 프로그램 노드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationNode::Detach](../../winscript/reference/idebugapplicationnode-detach.md)   
 [IDebugApplicationNode 인터페이스](../../winscript/reference/idebugapplicationnode-interface.md)