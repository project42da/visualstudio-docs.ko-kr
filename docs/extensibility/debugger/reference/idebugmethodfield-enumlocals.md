---
title: IDebugMethodField::EnumLocals | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMethodField::EnumLocals
helpviewer_keywords: IDebugMethodField::EnumLocals method
ms.assetid: b0456a6d-2b96-49e2-a871-516571b4f6a5
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa4ab5a8963ae8364e35cdc0e2a5237a75d35994
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmethodfieldenumlocals"></a>IDebugMethodField::EnumLocals
메서드의 선택한 지역 변수에 대 한 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAddress`  
 [in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 컨텍스트 또는 지역 변수를 얻을 수 있는 범위를 선택 하는 디버그 주소를 나타내는 개체입니다.  
  
 `ppLocals`  
 [out] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 지역 변수 목록을 나타내는 개체입니다; 그렇지 않으면 로컬 항목 없음 없는 경우 null 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 하거나 로컬 항목 없음 없으면 S_FALSE를 반환 합니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 지정 된 디버그 주소를 포함 하는 블록 내에 정의 된 변수만 열거 됩니다. 모든 컴파일러에서 생성 된 지역 변수를 포함 하 여 모든 지역, 필요한 경우 호출 된 [EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md) 메서드.  
  
 메서드는 컨텍스트 또는 블록에 대 한 여러 범위 지정 포함 될 수 있습니다. 예를 들어 다음 인위적인된 메서드는 세 가지 범위, 두 개의 내부 블록 및 메서드 본문을 포함합니다.  
  
```csharp  
public void func(int index)  
{  
    // Method body scope  
    int a = 0;  
    if (index == 1)  
    {  
        // Inner scope 1  
        int temp1 = a;  
    }  
    else  
    {  
        // Inner scope 2  
        int temp2 = a;  
    }  
}  
```  
  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) 개체가 나타내는 `func` 메서드 자체입니다. 호출는 `EnumLocals` 사용 하 여 메서드는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 로 설정는 `Inner Scope 1` 반환 되 고, 포함 하는 열거형은 `temp1` 예를 들어 변수 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)