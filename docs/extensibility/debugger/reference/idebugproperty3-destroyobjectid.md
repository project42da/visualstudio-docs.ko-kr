---
title: IDebugProperty3::DestroyObjectID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0db5ef80a1734aedb819c109aa4c27c40224886e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
호출자에 게 고유 하 게 다른 모든 속성에서에서이 속성을 식별 더 이상 더 관심이 있는지를 나타내는이 속성과 연결 된 고유 ID를 제거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 디버그 엔진 (이미 추적을 내부적으로 고유 하 게) 이므로 속성에 대 한 고유 Id를 지 원하는 데 필요 하지 않은 경우, 단순히 반환 수 `E_NOTIMPL` 이 메서드에 대 한 합니다.  
  
 고유 Id에 대 한 호출을 사용 하 여 만들어진는 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) 메서드 호출자에 게 다른 모든 속성과 함께이 속성은 고유 하 게 식별 하 고 있는지 확인 하려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)