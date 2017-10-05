---
title: IDebugPort2::GetPortRequest | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPort2::GetPortRequest
helpviewer_keywords:
- IDebugPort2::GetPortRequest
ms.assetid: 14abf847-0675-4fa8-872e-971e00c84224
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
ms.openlocfilehash: 58968a42b433ab87f556ff2dfbeb899fdcf3a681
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="idebugport2getportrequest"></a>IDebugPort2::GetPortRequest
이전에 (있는 경우) 포트를 만드는 데 사용 하는 포트에 대 한 설명을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPortRequest(   
   IDebugPortRequest2** ppRequest  
);  
```  
  
```csharp  
int GetPortRequest(   
   out IDebugPortRequest2 ppRequest  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppRequest`  
 [out] 반환 된 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) 포트를 만드는 데 사용 하는 요청을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  반환 `E_PORT_NO_REQUEST` 포트를 사용 하 여 만들어지지 않은 경우는 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) 포트 요청 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)   
 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)
