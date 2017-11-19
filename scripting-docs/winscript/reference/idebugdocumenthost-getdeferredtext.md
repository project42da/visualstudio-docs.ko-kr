---
title: IDebugDocumentHost::GetDeferredText | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentHost.GetDeferredText
apilocation: scrobj.dll
helpviewer_keywords: IDebugDocumentHost::GetDeferredText
ms.assetid: 527da666-fef5-4db3-a319-e68d466a7721
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ace3bdbfef143a3307d81455788a1e81788cb50b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthostgetdeferredtext"></a>IDebugDocumentHost::GetDeferredText
사용 하 여 추가 된 문자 범위를 반환 합니다.는 `IDebugDocumentHelper::AddDeferredText` 메서드는 원래 호스트 문서에서 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDeferredText(  
   DWORD              dwTextStartCookie,  
   WCHAR*             pcharText,  
   SOURCE_TEXT_ATTR*  pstaTextAttr,  
   ULONG*             pcNumChars,  
   ULONG              cMaxChars  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwTextStartCookie`  
 [in] 텍스트의 시작 위치를 나타내는 호스트 정의 쿠키입니다.  
  
 `pcharText`  
 [out에서] 문자 텍스트 버퍼입니다. 이 메서드는 경우이 매개 변수는 문자를 반환 하지 않습니다 `NULL`합니다.  
  
 `pstaTextAttr`  
 [out에서] 문자 특성이 버퍼입니다. 이 매개 변수가이 메서드는 특성을 반환 하지 `NULL`합니다.  
  
 `pcNumChars`  
 [out에서] 반환 된 문자/특성의 실제 수를 나타냅니다. 이 매개 변수는이 메서드를 호출 하기 전에 0으로 설정 되어야 합니다.  
  
 `cMaxChars`  
 [in] 반환할 문자 최대 수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|메서드가 구현 되지 않았습니다.|  
  
## <a name="remarks"></a>설명  
 이 반환 될 수 있으며 `E_NOTIMPL`호스트를 호출 하지 않는 경우, `IDebugDocumentHelper::AddDeferredText`합니다.  
  
> [!NOTE]
>  이 메서드는 원래 문서에서 텍스트를 반환합니다. 호스트는를 추적 하지 편집 또는 문서에 다른 변경 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHost 인터페이스](../../winscript/reference/idebugdocumenthost-interface.md)   
 [IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [SOURCE_TEXT_ATTR 열거형](../../winscript/reference/source-text-attr-enumeration.md)