---
title: IDebugDocumentHelper::BringDocumentContextToTop | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentHelper.BringDocumentContextToTop
apilocation: pdm.dll
helpviewer_keywords: IDebugDocumentHelper::BringDocumentContextToTop
ms.assetid: cf9751c5-e9b7-45c6-b084-3f3873dbf01d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 665d194abd2eed02096a2295ec0683a03830fb8d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthelperbringdocumentcontexttotop"></a>IDebugDocumentHelper::BringDocumentContextToTop
디버거 사용자 인터페이스에서 위쪽을이 설명서의 컨텍스트를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT BringDocumentContextToTop(  
   IDebugDocumentContext*  pddc  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pddc`  
 문서 디버거 사용자 인터페이스의 맨 위로 가져올 컨텍스트.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버거 사용자 인터페이스에 위쪽을이 문서의 컨텍스트를 가져옵니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)