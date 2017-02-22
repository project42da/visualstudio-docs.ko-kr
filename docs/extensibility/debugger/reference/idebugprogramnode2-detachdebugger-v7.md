---
title: "IDebugProgramNode2::DetachDebugger_V7 | Microsoft Docs"
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
  - "IDebugProgramNode2::DetachDebugger"
helpviewer_keywords: 
  - "IDebugProgramNode2::DetachDebugger"
  - "IDebugProgramNode2::DetachDebugger_V7"
ms.assetid: d2d4b78e-a2dd-4217-97a6-ab648fd2ee2f
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramNode2::DetachDebugger_V7
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용 되지 않습니다.  사용 하지 않습니다.  
  
## 구문  
  
```cpp#  
HRESULT DetachDebugger_V7 (   
   void   
);  
```  
  
```c#  
int DetachDebugger_V7 ();  
```  
  
## 반환 값  
 구현은 항상 반환 해야 `E_NOTIMPL`.  
  
## 설명  
  
> [!WARNING]
>  로 [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)]에서이 메서드는 더 이상 사용 되며 항상 반환 해야 `E_NOTIMPL`.  
  
 디버거 예기치 않게 종료 될 때이 메서드가 호출 됩니다.  이 메서드를 호출 하면는 DE 사용자 로부터 분리 하는 것 처럼 프로그램을 계속 합니다.  디버그 이벤트가 더 이상 보낼 수 있습니다.  프로그램이 다른 디버거 인스턴스를 연결할 수 있는 상태 여야 합니다.  
  
## 참고 항목  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)