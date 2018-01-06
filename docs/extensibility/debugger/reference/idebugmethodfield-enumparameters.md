---
title: IDebugMethodField::EnumParameters | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMethodField::EnumParameters
helpviewer_keywords: IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f60fbde074f660647aedd65a7bae7f98576d485d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
메서드의 매개 변수에 대 한 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppParams`  
 [out] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 메서드에 매개 변수 목록을 나타내는 개체입니다; 그렇지 않으면 매개 변수가 없는 경우 null 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 하거나 매개 변수가 없는 경우 S_FALSE를 반환 합니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 각 요소는 한 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 다른 형식의 매개 변수를 나타내는 개체입니다. 호출 된 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 정확히 어떤 종류의 매개 변수 개체가 나타내는 확인 하려면 각 개체에 대해 메서드.  
  
 매개 변수 이름 및 해당 형식 둘 다 포함 되어 있습니다. 클래스 메서드는 첫 번째 매개 변수는 일반적으로 "this"이 포인터입니다.  
  
 매개 변수 형식, 필요한 경우에 호출는 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)