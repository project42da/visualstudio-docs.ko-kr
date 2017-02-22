---
title: "IDebugProgramNodeAttach2::OnAttach | Microsoft Docs"
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
  - "IDebugProgramNodeAttach2::OnAttach"
helpviewer_keywords: 
  - "IDebugProgramNodeAttach2::OnAttach"
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
caps.latest.revision: 3
caps.handback.revision: 3
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramNodeAttach2::OnAttach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

관련된 프로그램에 연결 또는 연결 프로세스를 지연의 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 방법입니다.  
  
## 구문  
  
```cpp#  
HRESULT OnAttach(  
   [in] REFGUID guidProgramId  
);  
```  
  
```c#  
int OnAttach(  
   ref Guid guidProgramId  
};  
```  
  
#### 매개 변수  
 `guidProgramId`  
 \[in\] `GUID` 관련된 프로그램에 할당할 수 있습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 경우는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드를 호출 하면 안 됩니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 연결 하는 동안이 메서드 전에 호출에서 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드가 호출 됩니다.  `OnAttach` 메서드는 연결 프로세스를 수행할 수 있습니다 \(경우에이 메서드는 반환 `S_FALSE`\) 또는 연결 프로세스를 지연의 `IDebugEngine2::Attach` 메서드 \(는 `OnAttach` 메서드가 반환 `S_OK`\).  이벤트는 `OnAttach` 메서드를 설정할 수 있습니다의 `GUID` 으로 디버깅 중인 프로그램의를 주어진 `GUID`.  
  
## 참고 항목  
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)