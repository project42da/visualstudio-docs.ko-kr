---
title: "IEnumDebugBoundBreakpoints2::Reset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugBoundBreakpoints2::Reset"
helpviewer_keywords: 
  - "IEnumDebugBoundBreakpoints2::Reset"
ms.assetid: 0f0522a5-6a97-4c4e-859b-cc4476e6c527
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IEnumDebugBoundBreakpoints2::Reset
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

열거형의 첫 번째 요소를 다시 설정합니다.  
  
## 구문  
  
```cpp#  
HRESULT Reset(  
   void  
);  
```  
  
```c#  
int Reset();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드 호출 후에 다음 호출을 [다음](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md) 메서드 열거형의 첫 번째 요소를 반환 합니다.  
  
## 참고 항목  
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)