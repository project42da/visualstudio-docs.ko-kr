---
title: IDebugDocumentProvider::GetDocument | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentProvider.GetDocument
apilocation: pdm.dll
helpviewer_keywords: IDebugDocumentProvider::GetDocument
ms.assetid: da67dab0-778a-4dab-8ca3-055ee7a4f141
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8dd952a63253dbbf6034e0345547e2bec73b60c2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumentprovidergetdocument"></a>IDebugDocumentProvider::GetDocument
로 인해 문서가 아직 없는 경우 인스턴스화할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDocument(  
   IDebugDocument**  ppssd  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppssd`  
 [out] 문서에 해당 하는 디버그 문서입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 방법을 사용 하면 문서 아직 없는 경우 인스턴스화할 수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentProvider 인터페이스](../../winscript/reference/idebugdocumentprovider-interface.md)