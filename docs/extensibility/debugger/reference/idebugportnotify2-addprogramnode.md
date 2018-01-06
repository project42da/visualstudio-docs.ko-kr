---
title: IDebugPortNotify2::AddProgramNode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortNotify2::AddProgramNode
helpviewer_keywords: IDebugPortNotify2::AddProgramNode
ms.assetid: 34c0e949-1eb9-4108-9cb8-a3eb87fcf190
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8516df0e1aaae5dbc21a962108e3120bf5a16d33
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportnotify2addprogramnode"></a>IDebugPortNotify2::AddProgramNode
실행 되는 포트를 디버깅할 수 있는 프로그램을 등록 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AddProgramNode(   
   IDebugProgramNode2* pProgramNode  
);  
```  
  
```csharp  
int AddProgramNode(   
   IDebugProgramNode2 pProgramNode  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pProgramNode`  
 [in] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 등록할 수 있도록 프로그램을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 프로그램 노드 등록 취소할 수 있습니다 포트에서 호출 하 여는 [RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)