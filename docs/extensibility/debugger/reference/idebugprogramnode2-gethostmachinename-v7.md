---
title: IDebugProgramNode2::GetHostMachineName_V7 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramNode2::GetHostMachineName
helpviewer_keywords:
- IDebugProgramNode2::GetHostMachineName_V7
- IDebugProgramNode2::GetHostMachineNameIDebugProgramNode2::GetHostMachineName
ms.assetid: a992f2c9-f68b-4146-8cc2-027753bf7ce6
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 536fc9d8b83f21141abb1db05066232ea48382de
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogramnode2gethostmachinenamev7"></a>IDebugProgramNode2::GetHostMachineName_V7
사용 되지 않습니다. 사용 하지 마십시오.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHostMachineName_V7 (   
   BSTR* pbstrHostMachineName  
);  
```  
  
```csharp  
int GetHostMachineName_V7 (   
   out string pbstrHostMachineName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrHostMachineName`  
 [out] 프로그램이 실행 중인 컴퓨터의 이름을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 구현을 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="remarks"></a>설명  
  
> [!WARNING]
>  일부로 [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)],이 메서드는 더 이상 사용 하며 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)