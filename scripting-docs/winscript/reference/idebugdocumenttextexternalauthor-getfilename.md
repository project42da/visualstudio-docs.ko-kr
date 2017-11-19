---
title: IDebugDocumentTextExternalAuthor::GetFileName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentTextExternalAuthor.GetFileName
apilocation: pdm.dll
helpviewer_keywords: IDebugDocumentTextExternalAuthor::GetFileName
ms.assetid: 87acdce6-acb2-4936-80dd-d624bb7dbd42
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9fc2532530044b7b3da286bce95152c704bf2392
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenttextexternalauthorgetfilename"></a>IDebugDocumentTextExternalAuthor::GetFileName
경로 정보 없이 문서의 이름을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFileName(  
   BSTR*  pbstrShortName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrShortName`  
 [out] 문서의 짧은 이름을 포함 하는 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 경로 정보 없이 문서의 이름을 반환합니다. 짧은 이름 대화 상자에서 일반적으로 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentTextExternalAuthor 인터페이스](../../winscript/reference/idebugdocumenttextexternalauthor-interface.md)