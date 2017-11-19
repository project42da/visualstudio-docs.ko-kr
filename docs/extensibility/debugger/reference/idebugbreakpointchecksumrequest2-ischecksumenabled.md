---
title: IDebugBreakpointChecksumRequest2::IsChecksumEnabled | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugBreakpointChecksumRequest2::IsChecksumEnabled
ms.assetid: 8b1853b5-745c-4cd6-88a9-ce0673971bb0
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7386ab585ac054e40e08ff2e4cf5f5d84fe8ab30
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugbreakpointchecksumrequest2ischecksumenabled"></a>IDebugBreakpointChecksumRequest2::IsChecksumEnabled
이 문서에 대 한 체크섬을 사용할지 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsChecksumEnabled(   
   BOOL *pfChecksumEnabled  
);  
```  
  
```csharp  
public int IsChecksumEnabled(   
   out int pfChecksumEnabled  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfChecksumEnabled`  
 [out] TRUE를 반환 하는 체크섬은 사용할 수 있습니다. 그렇지 않으면 FALSE를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBreakpointChecksumRequest2](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2.md)