---
title: "IDebugProgram2::GetProgramId | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgram2::GetProgramId"
helpviewer_keywords: 
  - "IDebugProgram2::GetProgramId"
ms.assetid: 2c31c0aa-2b71-46c7-849c-356e237d26f8
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgram2::GetProgramId
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로그램에 대 한 GUID를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetProgramId(   
   GUID* pguidProgramId  
);  
```  
  
```c#  
int GetProgramId(   
   out Guid pguidProgramId  
);  
```  
  
#### 매개 변수  
 `pguidProgramId`  
 \[out\] 반환은 `GUID` 이 프로그램에 대 한.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 디버그 엔진 \(DE\) 원래 전달 프로그램 식별자를 반환 해야 합니다는 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 또는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 방법입니다.  구성 요소의 식별 프로그램을 디버거를 통해 있습니다.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)