---
title: IDebugEnumField::GetStringFromValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEnumField::GetStringFromValue
helpviewer_keywords: IDebugEnumField::GetStringFromValue method
ms.assetid: 5f95fd0c-fdce-497f-9f54-2ad8749494e9
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ed010734ec09af01c4a7abe6f8ceab0a93fdb482
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugenumfieldgetstringfromvalue"></a>IDebugEnumField::GetStringFromValue
이 메서드는 해당 값이 지정 열거형 상수 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStringFromValue(  
   ULONGLONG value,  
   BSTR*     pbstrValue  
);  
```  
  
```csharp  
int GetStringFromValue(  
   ulong      value,  
   out string pbstrValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value`  
 [in] 열거형의 이름을 가져오지 못했습니다 상수 값입니다.  
  
 `pbstrValue`  
 [out] 열거형 상수의 이름을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 값에 연결 된 이름은 하거나 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 동일한 값과 연결 된 이름을 여러 개 있으면 열거형에 정의 된 이름이 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)