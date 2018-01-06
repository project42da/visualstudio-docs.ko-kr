---
title: IDebugCoreServer2::GetPort | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer2::GetPort
helpviewer_keywords: IDebugCoreServer2::GetPort
ms.assetid: 3f5ea4a8-6085-4600-980a-9e48f8b5be56
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a51eefc5defb02f1affbbad8822296150186e060
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver2getport"></a>IDebugCoreServer2::GetPort
특정 포트를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPort(   
   REFGUID       guidPort,  
   IDebugPort2** ppPort  
);  
```  
  
```csharp  
int GetPort(   
   ref Guid        guidPort,  
   out IDebugPort2 ppPort  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidPort`  
 [in] 검색할 포트의 GUID입니다.  
  
 `ppPort`  
 [out] 반환 된 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 원하는 포트를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 반환 `E_PORTSUPPLIER_NO_PORT` 식별자로 포트가 없는 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)