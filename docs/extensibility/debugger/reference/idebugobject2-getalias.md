---
title: IDebugObject2::GetAlias | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject2::GetAlias
helpviewer_keywords: IDebugObject2::GetAlias method
ms.assetid: aa6824d5-c932-42ba-8713-950e7d1fb42f
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a487043d6c046a9c117c4845d56db2f18bf51896
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugobject2getalias"></a>IDebugObject2::GetAlias
있는 경우이 개체와 연결 된 별칭을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAlias(  
   IDebugAlias** ppAlias  
);  
```  
  
```csharp  
int GetAlias(  
   out IDebugAlias ppAlias  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppAlias`  
 [out] 반환 된 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) 이 개체에 대 한 별칭을 나타내는 개체입니다; 그렇지 않으면 null 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 개체에 대 한 별칭에 대 한 호출을 사용 하 여 만들어집니다는 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)