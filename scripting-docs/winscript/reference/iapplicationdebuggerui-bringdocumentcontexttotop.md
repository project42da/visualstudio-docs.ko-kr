---
title: IApplicationDebuggerUI::BringDocumentContextToTop | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IApplicationDebuggerUI.BringDocumentContextToTop
apilocation: scrobj.dll
helpviewer_keywords: IApplicationDebuggerUI::BringDocumentContextToTop
ms.assetid: 7844217d-658b-42af-8d10-2714f4eded20
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2fab017ab286957cf2c4be35832b1db877b339bd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iapplicationdebuggeruibringdocumentcontexttotop"></a>IApplicationDebuggerUI::BringDocumentContextToTop
디버거 사용자 인터페이스에서 위쪽으로 지정한 문서 컨텍스트를 포함 하는 창을 시작 하 고 컨텍스트에 창을 스크롤합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT BringDocumentContextToTop(  
   IDebugDocumentContext*  pddc  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pddc`  
 [in] 문서 디버거 사용자 인터페이스의 맨 위로 가져올 컨텍스트.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_INVALIDARG`|지정한 컨텍스트 `pddc` 알 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버거 사용자 인터페이스에서 위쪽으로 지정한 문서 컨텍스트를 포함 하는 창을 제공 하며 컨텍스트에 창을 스크롤합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IApplicationDebuggerUI 인터페이스](../../winscript/reference/iapplicationdebuggerui-interface.md)