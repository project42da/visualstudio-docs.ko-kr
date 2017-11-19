---
title: IDebugObject2::IsEncOutdated | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject2::IsEncOutdated
helpviewer_keywords: IDebugObject2::IsEncOutdated method
ms.assetid: d3a8c02d-895b-478c-9957-d663130f308e
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e8776288baf97ea9bf6b8c4b9b9f4a055ab88949
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugobject2isencoutdated"></a>IDebugObject2::IsEncOutdated
이 메서드는이 개체 또는 부모 컨테이너의 편집 하며 계속 하기 상태 최신 인지 확인 합니다. 사용자 지정 식 계산기가 메서드와 항상 반환 구현 하지 않는 `E_NOTIMPL`합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsEncOutdated(  
   BOOL* pfEncOutdated  
);  
```  
  
```csharp  
int IsEncOutdated(  
   out int pfEncOutdated  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfEncOutdated`  
 [out] 0이 아닌 (`TRUE`) 편집 하며 계속 하기 상태를 오래 된 경우에 0 (`FALSE`) 없는 경우.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
> [!NOTE]
>  사용자 지정 식 계산기는 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)