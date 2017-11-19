---
title: IDebugProcessSecurity::QueryCanSafelyAttach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0ad6b7ffde868bf6b9dc4f9ef3bab9d9094ab765
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocesssecurityquerycansafelyattach"></a>IDebugProcessSecurity::QueryCanSafelyAttach
이 메서드는 사용자는 안전 하지 않은 프로세스에 연결 하기 전에 경고를 표시 하려면 포트 공급자를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QueryCanSafelyAttach();  
```  
  
```csharp  
int QueryCanSafelyAttach();  
```  
  
## <a name="return-value"></a>반환 값  
 반환 값은 다음과 같습니다.  
  
-   `S_OK`: 프로세스에 연결 하는 것은 안전 하 고 경고 대화 상자가 표시 됩니다.  
  
-   `S_FALSE`: 보안 문제가 발생할 수 연결 하 고 경고와 함께 대화 상자가 표시 됩니다.  
  
-   `FAILURE`: 실패 프로세스에 연결 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)