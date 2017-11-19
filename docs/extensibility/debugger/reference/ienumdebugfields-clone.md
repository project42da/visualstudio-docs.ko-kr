---
title: IEnumDebugFields::Clone | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFields::Clone
helpviewer_keywords: IEnumDebugFields::Clone method
ms.assetid: 7ec265a8-696f-45ce-a2a2-0a83e96fee1b
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f1a4dec6d0cb769d4d49c55800d21b14fe6ebbef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugfieldsclone"></a>IEnumDebugFields::Clone
이 메서드는 별도 개체로 현재 열거형의 복사본을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Clone(  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnum`  
 [out] 이 열거형은 개별 개체로 복사본을 반환 합니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 열거형의 복사본이 메서드는 한 번에 원본과 동일한 상태를 있습니다. 그러나 원본 및 복사본의 상태 및는 별개임 개별적으로 변경할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)