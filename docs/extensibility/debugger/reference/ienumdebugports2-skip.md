---
title: IEnumDebugPorts2::Skip | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugPorts2::Skip
helpviewer_keywords: IEnumDebugPorts2::Skip
ms.assetid: a837383f-7b39-4e06-b336-f1715b073dbe
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a418713e9b1410145abaab9d048cdd1107313d0b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugports2skip"></a>IEnumDebugPorts2::Skip
지정 된 개수의 요소를 건너뜁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 건너뛸 요소 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우 `celt` 나머지 요소 수보다 큰 이며 그렇지 않은 경우 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 경우 `celt` 수보다 큰 값 나머지 요소 열거형 끝으로 설정 하 고 `S_FALSE` 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)