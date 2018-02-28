---
title: IDebugDocumentTextEvents::onReplaceText | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugDocumentTextEvents.onReplaceText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentTextEvents::onReplaceText
ms.assetid: 3cb053c4-1f7f-4aed-aee6-f8a9e9e69d29
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1cbe022113e8a97dc31b4cf5a2286ec0b5096d3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenttexteventsonreplacetext"></a>IDebugDocumentTextEvents::onReplaceText
텍스트 바뀌었음을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT onReplaceText(  
   ULONG  cCharacterPosition,  
   ULONG  cNumToReplace  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cCharacterPosition`  
 [in] 첫 번째 문자의 문자 위치를 교체 했습니다.  
  
 `cNumToReplace`  
 [in] 대체 되는 문자의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 텍스트 바뀌었음을 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentTextEvents 인터페이스](../../winscript/reference/idebugdocumenttextevents-interface.md)