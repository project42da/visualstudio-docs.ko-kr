---
title: IDebugProgramEngines2::SetEngine | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramEngines2::SetEngine
helpviewer_keywords: IDebugProgramEngines2::SetEngine
ms.assetid: c05857ee-89cf-455e-8f1e-300cce4a2eab
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: af62aec85afd39ee617b9b700e14168395269532
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogramengines2setengine"></a>IDebugProgramEngines2::SetEngine
프로그램 또는 프로그램 노드는 디버그 엔진 (DE)이이 프로그램을 디버깅 하는 데 알려 줍니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetEngine(   
   REFGUID guidEngine  
);  
```  
  
```csharp  
int SetEngine(   
   ref Guid guidEngine  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidEngine`  
 [in] DE의 GUID입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)