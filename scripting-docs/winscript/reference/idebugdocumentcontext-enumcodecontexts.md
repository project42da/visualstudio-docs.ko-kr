---
title: IDebugDocumentContext::EnumCodeContexts | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentContext.EnumCodeContexts
apilocation: pdm.dll
helpviewer_keywords: IDebugDocumentContext::EnumCodeContexts
ms.assetid: fb0aa64e-c458-4ef1-bcd8-5cebdc972549
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 300102d75fcfa797e8e073b9a1ce77cc5ee2827a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumentcontextenumcodecontexts"></a>IDebugDocumentContext::EnumCodeContexts
이 문서 컨텍스트와 연결 된 코드 컨텍스트를 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumCodeContexts(  
   IEnumDebugCodeContexts**  ppescc  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppescc`  
 [out] 이 문서 컨텍스트와 연결 된 코드 컨텍스트입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 문서는 문서가 포함 파일 또는 템플릿을 하지 않는 한 일반적으로 하나의 코드 컨텍스트와 연결 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentContext 인터페이스](../../winscript/reference/idebugdocumentcontext-interface.md)