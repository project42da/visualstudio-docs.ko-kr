---
title: IDebugPortSupplier2::AddPort | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPortSupplier2::AddPort
helpviewer_keywords:
- IDebugPortSupplier2::AddPort
ms.assetid: df491161-6bf3-4fcc-b478-b9ec88ec995f
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 2845b7c3d10b62c268843f934cf3730019afd657
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="idebugportsupplier2addport"></a>IDebugPortSupplier2::AddPort
포트를 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AddPort(   
   IDebugPortRequest2* pRequest,  
   IDebugPort2**       ppPort  
);  
```  
  
```csharp  
int AddPort(   
   IDebugPortRequest2 pRequest,  
   out IDebugPort2    ppPort  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRequest`  
 [in] [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) 추가할 포트를 설명 하는 개체입니다.  
  
 `ppPort`  
 [out] 반환 된 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 포트를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 실제로 active 포트의 포트 공급 업체의 내부 목록에 추가할 뿐 아니라 요청 된 포트를 만듭니다. [CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) 가능한 시간이 많이 걸리는 지연 되지 않도록 하려면 메서드를 처음 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)
