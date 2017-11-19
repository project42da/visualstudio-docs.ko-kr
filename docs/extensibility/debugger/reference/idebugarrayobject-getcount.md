---
title: IDebugArrayObject::GetCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugArrayObject::GetCount
helpviewer_keywords: IDebugArrayObject::GetCount method
ms.assetid: 7931f3f7-033c-4bf8-8abd-95183952ebb0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7c7a860dd1039f5b2e5a2049674ba78a91af7741
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugarrayobjectgetcount"></a>IDebugArrayObject::GetCount
배열의 요소 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
[C++]  
HRESULT GetCount(   
   DWORD* pdwElements  
);  
```  
  
```  
[C#]  
int GetCount(  
   out uint pdwElements  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwElements`  
 [out] 개수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 배열 개체는 다차원 배열 하는 경우에 배열 개체의 요소를 모두 1 차원 배열에으로 간주 합니다. 예를 들어 배열의 지정 된 `myarray[3][2][6]`,이 메서드는 반환에 36의 `pdwElements` 매개 변수입니다. 사용 하 여는 [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) 메서드를 한 번에 하나씩 개별 요소를 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)