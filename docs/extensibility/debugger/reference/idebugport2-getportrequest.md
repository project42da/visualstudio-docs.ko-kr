---
title: IDebugPort2::GetPortRequest | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPort2::GetPortRequest
helpviewer_keywords:
- IDebugPort2::GetPortRequest
ms.assetid: 14abf847-0675-4fa8-872e-971e00c84224
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6897c3085f14be785e4baaace0de7a4e92fea9ae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
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