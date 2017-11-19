---
title: IDebugDocumentText::GetLineOfPosition | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentText.GetLineOfPosition
apilocation: pdm.dll
helpviewer_keywords: IDebugDocumentText::GetLineOfPosition
ms.assetid: fe8d4802-ea16-49ca-8973-89dcaf6c915b
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2512fa3b56a19ed7396c7a351c8d8f8323fff6f5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenttextgetlineofposition"></a>IDebugDocumentText::GetLineOfPosition
지정된 된 문자 위치에 줄 번호 및 필요에 따라 해당 하는 줄 내에서 문자 오프셋을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetLineOfPosition(  
   ULONG   cCharacterPosition,  
   ULONG*  pcLineNumber,  
   ULONG*  pcCharacterOffsetInLine  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cCharacterPosition`  
 [in] 시작 문자 위치 범위의 위치입니다.  
  
 `pcLineNumber`  
 [out] 줄 번호의 범위입니다.  
  
 `pcCharacterOffsetInLine`  
 [out에서] 줄 범위의 문자 오프셋 `pcLineNumber`합니다. 이 매개 변수가 `NULL`, 메서드는 값을 반환 하지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 지정 된 문자 위치에 줄 번호 및 필요에 따라 해당 하는 줄 내에서 문자 오프셋을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentText 인터페이스](../../winscript/reference/idebugdocumenttext-interface.md)