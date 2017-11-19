---
title: IDebugCoreServer3::GetServerFriendlyName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer3::GetServerFriendlyName
helpviewer_keywords: IDebugCoreServer3::GetServerFriendlyName
ms.assetid: 7035b904-b3d7-4d9b-98d9-65714b8a8b9f
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9ad20c8b71132b87efae6f2b4d27b7339e574cc4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcoreserver3getserverfriendlyname"></a>IDebugCoreServer3::GetServerFriendlyName
서버에 대 한 친숙 한 이름을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetServerFriendlyName(  
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetServerFriendlyName(  
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrName`  
 [out] 서버에 대 한 친숙 한 이름을 반환합니다.  
  
> [!NOTE]
>  호출자는 문자열을 해제 하는 일을 담당 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 사용자 시작 서버에 대 한이 메서드에서 반환 된 이름은 서버의 전체 이름입니다. 자동 시작 서버에 대 한 이름은 컴퓨터의 서버가 실행 중인지입니다.  
  
 컴퓨터 지향 이름에 대 한 호출에서 [GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md)