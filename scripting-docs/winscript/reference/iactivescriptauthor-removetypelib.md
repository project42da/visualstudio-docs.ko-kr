---
title: IActiveScriptAuthor::RemoveTypeLib | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptAuthor.RemoveTypeLib
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptAuthor::RemoveTypeLib
ms.assetid: 232c3698-024d-4549-8fbc-cb0d3ac17dc5
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 91d44d2f910a1523d0c45871e01d0258dcdd4138
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthorremovetypelib"></a>IActiveScriptAuthor::RemoveTypeLib
엔진 네임 스페이스를 제작 하는 스크립트에서 형식 라이브러리를 제거 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemoveTypeLib(  
   REFGUID   rguidTypeLib,  
   DWORD     dwMajor,  
   DWORD     dwMinor  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rguidTypeLib`  
 [in] CLSID (클래스 식별자)의 형식 라이브러리를 제거 하려면.  
  
 `dwMajor`  
 [in] 주 버전 번호입니다.  
  
 `dwMinor`  
 [in] 부 버전 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)