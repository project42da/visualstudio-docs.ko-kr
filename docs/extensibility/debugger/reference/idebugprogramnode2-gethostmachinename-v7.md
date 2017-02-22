---
title: "IDebugProgramNode2::GetHostMachineName_V7 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramNode2::GetHostMachineName"
helpviewer_keywords: 
  - "IDebugProgramNode2::GetHostMachineName_V7"
  - "IDebugProgramNode2::GetHostMachineNameIDebugProgramNode2::GetHostMachineName"
ms.assetid: a992f2c9-f68b-4146-8cc2-027753bf7ce6
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramNode2::GetHostMachineName_V7
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용 되지 않습니다.  사용 하지 않습니다.  
  
## 구문  
  
```cpp#  
HRESULT GetHostMachineName_V7 (   
   BSTR* pbstrHostMachineName  
);  
```  
  
```c#  
int GetHostMachineName_V7 (   
   out string pbstrHostMachineName  
);  
```  
  
#### 매개 변수  
 `pbstrHostMachineName`  
 \[out\] 프로그램이 실행 되 고 있는 컴퓨터의 이름을 반환 합니다.  
  
## 반환 값  
 구현은 항상 반환 해야 `E_NOTIMPL`.  
  
## 설명  
  
> [!WARNING]
>  로 [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)]에서이 메서드는 더 이상 사용 되며 항상 반환 해야 `E_NOTIMPL`.  
  
## 참고 항목  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)