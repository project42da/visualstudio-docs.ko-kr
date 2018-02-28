---
title: IDebugDocumentTextEvents::onUpdateDocumentAttributes | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugDocumentTextEvents.onUpdateDocumentAttributes
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentTextEvents::onUpdateDocumentAttributes
ms.assetid: 48fa909c-14c2-4ca4-af86-a5809c72dd39
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef9313f612d539e3068c2dd4bb20eb5d343fc53b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenttexteventsonupdatedocumentattributes"></a>IDebugDocumentTextEvents::onUpdateDocumentAttributes
문서 속성 변경 되었음을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT onUpdateDocumentAttributes(  
   TEXT_DOC_ATTR  textdocattr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `textdocattr`  
 [in] 새 문서 특성입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 문서 특성이 변경 되었음을 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentTextEvents 인터페이스](../../winscript/reference/idebugdocumenttextevents-interface.md)   
 [TEXT_DOC_ATTR 상수](../../winscript/reference/text-doc-attr-constants.md)