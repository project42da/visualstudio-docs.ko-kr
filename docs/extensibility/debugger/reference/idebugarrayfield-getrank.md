---
title: IDebugArrayField::GetRank | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugArrayField::GetRank
helpviewer_keywords: IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2467c8d4ed85a685de80511d68a20e24c047306e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
순위 또는 배열의 차원 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwRank`  
 [out] 순위를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 배열의 차수 차원 수에 해당합니다. C + + 및 C#에서는 다차원 배열은 실제로 배열의 배열 및 1 차원 배열 방금 없으므로 간주할 수 (및 `GetRank` 메서드는 항상 1 반환). [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)], 반면에 다차원 배열은 다르게 처리 되 고 차원 수를 반영 하는 이러한 배열 차수 (및 `GetRank` 메서드는 항상 차원 수가 반환).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)