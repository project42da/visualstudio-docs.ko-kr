---
title: IDebugDocumentHelper::SetDebugDocumentHost | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentHelper.SetDebugDocumentHost
apilocation: pdm.dll
helpviewer_keywords: IDebugDocumentHelper::SetDebugDocumentHost
ms.assetid: b26a03c3-8a3f-47b0-b916-4c65d5500f10
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5d1377edaa5b10a7ebb06713e512010be010a9d3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthelpersetdebugdocumenthost"></a>IDebugDocumentHelper::SetDebugDocumentHost
설정 된 `IDebugDocumentHost` 이 문서에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetDebugDocumentHost(  
   IDebugDocumentHost*  pddh  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pddh`  
 [in] 디버그 문서 호스트입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 `IDebugDocumentHost` 인터페이스 스마트 호스트 구문 색 지정에 사용 됩니다, 지연 된 텍스트를 가져오고 새로 생성에 대 한 제어 개체를 반환 합니다. 컨텍스트 문서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHost 인터페이스](../../winscript/reference/idebugdocumenthost-interface.md)