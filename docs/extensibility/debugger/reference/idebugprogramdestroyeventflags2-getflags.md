---
title: "IDebugProgramDestroyEventFlags2::GetFlags | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetFlags"
  - "IDebugProgramDestroyEventFlags2::GetFlags"
ms.assetid: dd53bd0c-459a-4077-ba81-780defb71e87
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramDestroyEventFlags2::GetFlags
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램 검색 플래그를 파괴 하십시오.  
  
## 구문  
  
```cpp#  
HRESULT GetFlags(  
   PROGRAM_DESTROY_FLAGS* pdwFlags  
);  
```  
  
```c#  
public int GetFlags(  
   out enum_PROGRAM_DESTROY_FLAGS pdwFlags  
);  
```  
  
#### 매개 변수  
 `pdwFlags`  
 \[out\] 프로그램을 나타내는 플래그를 파괴 하십시오.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugProgramDestroyEventFlags2](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2.md)   
 [PROGRAM\_DESTROY\_FLAGS](../../../extensibility/debugger/reference/program-destroy-flags.md)