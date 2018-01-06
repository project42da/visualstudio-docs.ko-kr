---
title: IDebugDefaultPort2::GetPortNotify | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDefaultPort2::GetPortNotify
helpviewer_keywords: IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 26eefb5dc1e30d9d9b8b6584159ce5f942b8e4e0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
이 메서드를 가져옵니다는 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) 이 포트에 대 한 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPortNotify(  
   IDebugPortNotify2** ppPortNotify  
);  
```  
  
```csharp  
int GetPortNotify(  
   out IDebugPortNotify2 ppPortNotify  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppPortNotify`  
 [out] [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 `QueryInterface` 메서드가 구현 하는 개체에서 호출 되는 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 가져오는 인터페이스를는 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) 인터페이스입니다. 그러나 다른 개체에는 원하는 인터페이스를 구현 하는 경우도 있습니다. 이 메서드는 이러한 상황을 숨깁니다 하 고 반환 된 `IDebugPortNotify2` 가장 적합 한 개체의 인터페이스.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)