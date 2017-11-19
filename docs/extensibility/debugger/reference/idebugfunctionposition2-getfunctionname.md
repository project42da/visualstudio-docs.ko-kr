---
title: IDebugFunctionPosition2::GetFunctionName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugFunctionPosition2::GetFunctionName
helpviewer_keywords: IDebugFunctionPosition2::GetFunctionName
ms.assetid: eb7a348e-a7f5-4f25-be68-80482d5482a8
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 15329895493359a6054209fa1688a9870b4deb67
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugfunctionposition2getfunctionname"></a>IDebugFunctionPosition2::GetFunctionName
이 위치 가리키는 함수의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFunctionName(   
   BSTR* pbstrFunctionName  
);  
```  
  
```csharp  
int GetFunctionName(  
   out string pbstrFunctionName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrFunctionName`  
 [out] 함수의 이름을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)