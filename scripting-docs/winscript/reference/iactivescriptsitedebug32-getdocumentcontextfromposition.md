---
title: IActiveScriptSiteDebug32::GetDocumentContextFromPosition | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53348dff-35a6-4303-b263-90c10af06bf3
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 71136a1b3cb136cbc0a97cf39f59f1f4e950048b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitedebug32getdocumentcontextfromposition"></a>IActiveScriptSiteDebug32::GetDocumentContextFromPosition
위임 하는 언어 엔진에서 사용 하는 `IDebugCodeContext::GetSourceContext`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDocumentContextFromPosition(  
   DWORD_PTR                dwSourceContext,  
   ULONG                    uCharacterOffset,  
   ULONG                    uNumChars,  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwSourceContext`  
 [in] 에 제공 되는 원본 콘텐츠 `ParseScriptText` 또는 `AddScriptlet`합니다.  
  
 `uCharacterOffset`  
 [in] 문자 스크립틀릿 또는 스크립트 블록의 시작에 상대적으로 오프셋입니다.  
  
 `uNumChars`  
 [in] 이 컨텍스트에서 문자 수입니다.  
  
 `ppsc`  
 [out] 이 문자 위치 범위에 해당 하는 문서 컨텍스트.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 위임 하려면이 메서드를 사용 하는 언어 엔진 `IDebugCodeContext::GetSourceContext`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSiteDebug32 인터페이스](../../winscript/reference/iactivescriptsitedebug32-interface.md)