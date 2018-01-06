---
title: IDebugDefaultPort2::QueryIsLocal | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDefaultPort2::QueryIsLocal
helpviewer_keywords: IDebugDefaultPort2::QueryIsLocal
ms.assetid: 1a42e774-c6ed-419a-a0e3-cab5778652ca
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d52ee13002cc53084bc4f81b8cb65d489f3932d8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdefaultport2queryislocal"></a>IDebugDefaultPort2::QueryIsLocal
이 메서드는이 포트는 로컬 컴퓨터에 있는지 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QueryIsLocal(  
   void  
);  
```  
  
```csharp  
int QueryIsLocal();  
```  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 경우이 포트는 로컬 (호출자와 동일한 컴퓨터)에서 또는 `S_FALSE` 포트가 다른 컴퓨터에 있을 경우.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)