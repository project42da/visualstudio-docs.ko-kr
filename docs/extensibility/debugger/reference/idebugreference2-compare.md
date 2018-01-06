---
title: IDebugReference2::Compare | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugReference2::Compare
helpviewer_keywords: IDebugReference2::Compare
ms.assetid: 3361c495-2673-4b7c-82e3-dee74e1fa58d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 58469437dfca59e53403e2d128310a8440e30a19
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugreference2compare"></a>IDebugReference2::Compare
다른에 대 한 참조가 비교합니다. 나중에 사용하기 위해 예약되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Compare (   
   REFERENCE_COMPARE dwCompare,  
   IDebugReference2* pReference  
);  
```  
  
```csharp  
int Compare (   
   enum_REFERENCE_COMPARE dwCompare,  
   IDebugReference2       pReference  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwCompare`  
 [in] 값은 [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md) 비교 연산 예를 들어 보다 크거나 같음, 보다 작음, 지정 하는 열거형입니다.  
  
 `pReference`  
 [in] [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 과 비교할 수에 대 한 참조를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md)