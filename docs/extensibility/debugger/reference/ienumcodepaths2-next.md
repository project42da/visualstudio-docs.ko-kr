---
title: IEnumCodePaths2::Next | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumCodePaths2::Next
helpviewer_keywords: IEnumCodePaths2::Next
ms.assetid: c7a8fe97-2abc-4cee-8aef-64f1daa93b5c
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7a018e033d9e342697cd1e06d1ef9ad8a53e4036
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumcodepaths2next"></a>IEnumCodePaths2::Next
열거형에서 다음 요소 집합을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next(  
   ULONG       celt,  
   CODE_PATH** rgelt,  
   ULONG*      pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint        celt,  
   CODE_PATH[] rgelt,  
   ref uint    pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 검색할 요소의 수입니다. 또한의 최대 크기를 지정 된 `rgelt` 배열입니다.  
  
 `rgelt`  
 [out에서] 배열 [CODE_PATH](../../../extensibility/debugger/reference/code-path.md) 요소를 채워야 합니다.  
  
 `pceltFetched`  
 [out] 에 실제로 반환 된 요소의 수를 반환 `rgelt`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 요소 요청 된 수보다 적은지 반환 될 수 있습니다; 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)   
 [CODE_PATH](../../../extensibility/debugger/reference/code-path.md)