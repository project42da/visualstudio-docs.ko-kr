---
title: "IDebugCoreServer2::GetMachineUtilities_V7 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCoreServer2::GetMachineUtilities_V7"
helpviewer_keywords: 
  - "IDebugCoreServer2::GetMachineUtilities_V7"
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# IDebugCoreServer2::GetMachineUtilities_V7
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 서버에 대 한 시스템 유틸리티를 가져옵니다.  
  
> [!NOTE]
>  이 메서드는 사용 되지 않습니다: 사용 하지 마십시오 \([!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 항상 반환 `E_NOTIMPL` 이 메서드를 호출 하는 경우\).  이 역사적인 이유로 유지 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT GetMachineUtilities_V7(  
   IDebugMDMUtil2_V7** ppUtil  
);  
```  
  
```c#  
int GetMachineUtilities_V7(  
   out IDebugMDMUtil2_V7 ppUtil  
);  
```  
  
#### 매개 변수  
 `ppUtil`  
 \[out\] 반환 된 `IDebugMDMUtil2_V7` 시스템 정보 유틸리티를 나타내는 인터페이스입니다.  
  
## 반환 값  
 항상 반환 `E_NOTIMPL`에서 메서드가 구현 되지 않았음을 나타내는.  
  
## 설명  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]항상 반환 `E_NOTIMPL` 이 메서드를 호출 하면 됩니다.  
  
## 참고 항목  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)