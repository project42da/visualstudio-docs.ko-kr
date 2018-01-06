---
title: IDebugMethodField::EnumAllLocals | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMethodField::EnumAllLocals
helpviewer_keywords: IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2c8208b0d803dc5cbf6333f15cbda5b0f34bbd16
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
컴파일러에서 내부적으로 생성 된 항목을 포함 하 여 메서드의 모든 지역 변수에 대 한 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumAllLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumAllLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAddress`  
 [in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 특정 범위 또는 컨텍스트에서 가리키는 메서드 내에서 디버그 주소를 나타내는 개체입니다.  
  
 `ppLocals`  
 [out] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 지정된 된 범위에서 모든 지역 변수의 목록을 나타내는 개체; 그렇지 않으면 로컬 항목 없음 나타내는 null 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 하거나 로컬 항목 없음 없으면 S_FALSE를 반환 합니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 지정 된 디버그 주소를 포함 하는 블록 내에 정의 된 변수만 열거 됩니다. 이 메서드는 컴파일러에서 생성 된 지역 변수를 포함합니다. 명시적으로 호출 원본에 정의 된 지역 변수는 필요한 모든 경우는 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) 메서드.  
  
 메서드는 컨텍스트 또는 블록에 대 한 여러 범위 지정 포함 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)