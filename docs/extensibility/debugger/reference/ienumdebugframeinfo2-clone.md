---
title: IEnumDebugFrameInfo2::Clone | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFrameInfo2::Clone
helpviewer_keywords: IEnumDebugFrameInfo2::Clone
ms.assetid: cdd10489-1772-47e3-815f-a6cfd32a3c60
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 99455a18fb24e300e1139a7cb95af3230b8a3867
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugframeinfo2clone"></a>IEnumDebugFrameInfo2::Clone
별도 개체로 현재 열거형의 복사본을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Clone(  
   IEnumDebugFrameInfo2** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugFrameInfo2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnum`  
 [out] 이 열거형은 개별 개체로 복사본을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 열거형의 복사본이 메서드는 한 번에 원본과 동일한 상태를 있습니다. 그러나 원본 및 복사본의 상태 및는 별개임 개별적으로 변경할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)