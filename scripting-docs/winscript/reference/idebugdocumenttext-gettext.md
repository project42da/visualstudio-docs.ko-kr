---
title: IDebugDocumentText::GetText | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentText.GetText
apilocation: pdm.dll
helpviewer_keywords: IDebugDocumentText::GetText
ms.assetid: 3c940a30-6c0f-4deb-aa4d-21a0bdef8461
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5a1006304974fab4959ad6313ffdc26793cdd345
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenttextgettext"></a>IDebugDocumentText::GetText
문자 및/또는 문자 위치 범위와 연결 된 문자 특성을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetText(  
   ULONG              cCharacterPosition,  
   WCHAR*             pcharText,  
   SOURCE_TEXT_ATTR*  pstaTextAttr,  
   ULONG*             pcNumChars,  
   ULONG              cMaxChars  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cCharacterPosition`  
 [in] 시작 문자 위치 범위의 위치입니다.  
  
 `pcharText`  
 [out에서] 문자 텍스트 버퍼입니다. 버퍼는 저장할 수 있을 만큼 크기가 커야 합니다. `cMaxChars` 문자입니다. 이 매개 변수가 NULL 인 경우 메서드는 문자를 반환 하지 않습니다.  
  
 `pstaTextAttr`  
 [out에서] 문자 특성이 버퍼입니다. 버퍼는 저장할 수 있을 만큼 크기가 커야 합니다. `cMaxChars` 문자입니다. 이 매개 변수가 NULL 이면 메서드 특성을 반환 하지 않습니다.  
  
 `pcNumChars`  
 [out에서] 반환 된 문자/특성의 수입니다. 이 매개 변수는이 메서드를 호출 하기 전에 0으로 설정 되어야 합니다.  
  
 `cMaxChars`  
 [in] 문자 위치 범위에 있는 문자의 수입니다. 또한 반환할 문자의 최대 수를 지정 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 문자 및/또는 문자 위치 범위와 연결 된 문자 특성을 검색 합니다. 문자 위치 범위의 문자 위치와 문자 수가 지정 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentText 인터페이스](../../winscript/reference/idebugdocumenttext-interface.md)   
 [SOURCE_TEXT_ATTR 열거형](../../winscript/reference/source-text-attr-enumeration.md)