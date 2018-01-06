---
title: IDebugBinder3::GetTypeArgumentCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBinder3::GetTypeArgumentCount
helpviewer_keywords: IDebugBinder3::GetTypeArgumentCount method
ms.assetid: caf68de6-6f7c-4efd-b803-121347a5032e
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 99b1520aee230f58537aea1124be5277246b331e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbinder3gettypeargumentcount"></a>IDebugBinder3::GetTypeArgumentCount
이 메서드는이 개체와 연결 된 인수 형식 수를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeArgumentCount(  
   UINT* uCount  
);  
```  
  
```csharp  
int GetTypeArgumentCount(  
   out uint uCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `uCount`  
 [out] 이 개체와 연결 된 인수 형식 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드에 의해 반환 되는 값 배열을 할당 하 여 함께 사용할 데 사용할 수는 [GetTypeArguments](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [GetTypeArguments](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md)