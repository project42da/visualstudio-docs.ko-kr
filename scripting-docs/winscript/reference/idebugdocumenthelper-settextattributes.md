---
title: IDebugDocumentHelper::SetTextAttributes | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugDocumentHelper.SetTextAttributes
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::SetTextAttributes
ms.assetid: 31657738-9e4c-436a-be61-23f4185d452e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce837eda3a0d83a830e5d5e281b2d24cb932063a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthelpersettextattributes"></a>IDebugDocumentHelper::SetTextAttributes
범위의 텍스트를 재정의 그 텍스트에 다른 특성에 특성을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetTextAttributes(  
   ULONG              ulCharOffset,  
   ULONG              cChars,  
   SOURCE_TEXT_ATTR*  pstaTextAttr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ulCharOffset`  
 [in] 텍스트 범위의 시작 위치입니다.  
  
 `cChars`  
 [in] 범위에 있는 문자의 수입니다.  
  
 `pstaTextAttr`  
 [in] 텍스트의 범위에 대 한 소스 텍스트 특성입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 호출 하면 오류가 발생 `SetTextAttributes` 문서에 해당 텍스트를 추가 하기 전에 텍스트 범위에 있습니다. 호출 된 `AddDBCSText`, `AddUnicodeText`, 또는 `AddDeferredText` 문서에 텍스트를 추가 하는 방법입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)   
 [IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [SOURCE_TEXT_ATTR 열거형](../../winscript/reference/source-text-attr-enumeration.md)