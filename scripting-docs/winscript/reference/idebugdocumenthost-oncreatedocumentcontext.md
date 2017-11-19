---
title: IDebugDocumentHost::OnCreateDocumentContext | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentHost.OnCreateDocumentContext
apilocation: scrobj.dll
helpviewer_keywords: IDebugDocumentHost::OnCreateDocumentContext
ms.assetid: 080c8604-cfd7-484e-a337-15040870e683
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 55598a4191d421d3aea01d27cc7991b70bd6a019
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthostoncreatedocumentcontext"></a>IDebugDocumentHost::OnCreateDocumentContext
새 문서 컨텍스트를 만드는 중 이며 호스트가 필요에 따라 새 컨텍스트에 대 한 알 수 없는 제어를 반환할 수 있도록 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnCreateDocumentContext(  
   IUnknown**  ppunkOuter  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppunkOuter`  
 [out] 새 컨텍스트를 제어 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|호스트 제어 개체를 제공 하지 않습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하면 호스트 도우미 제공 문서 컨텍스트에 새 기능을 추가 합니다. 이 반환 될 수 있으며 **E_NOTIMPL** 또는 경우 호출자가 컨텍스트를 만드는 작업을 담당 인 null 외부 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHost 인터페이스](../../winscript/reference/idebugdocumenthost-interface.md)