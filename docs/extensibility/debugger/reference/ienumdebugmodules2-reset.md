---
title: "IEnumDebugModules2::Reset | Microsoft Docs"
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
  - "IEnumDebugModules2::Reset"
helpviewer_keywords: 
  - "IEnumDebugModules2::Reset"
ms.assetid: f6ff364c-2644-4919-b950-3cb82eb6f601
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugModules2::Reset
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
 이 메서드 호출 후에 다음 호출을 [다음](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md) 메서드 열거형의 첫 번째 요소를 반환 합니다.  
  
## 참고 항목  
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)