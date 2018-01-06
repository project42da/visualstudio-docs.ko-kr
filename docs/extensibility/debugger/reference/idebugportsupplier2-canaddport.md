---
title: IDebugPortSupplier2::CanAddPort | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortSupplier2::CanAddPort
helpviewer_keywords: IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6b493229ab33f628c54580711604b16a4e2b5c5b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
포트 공급자 새 포트를 추가할 수 있는지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CanAddPort(   
   void   
);  
```  
  
```csharp  
int CanAddPort();  
```  
  
## <a name="return-value"></a>반환 값  
 포트를 추가할 수 있으면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 를 나타내는 포트 없음이 포트 공급 업체에 추가할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 호출 하기 전에이 메서드를 호출 하는 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 포트도 추가 작업 시간이 많이 소요 될 수 있는 두 번째 방법을 만들어지므로 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)