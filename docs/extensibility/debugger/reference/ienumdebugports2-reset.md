---
title: "IEnumDebugPorts2::Reset | Microsoft Docs"
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
  - "IEnumDebugPorts2::Reset"
helpviewer_keywords: 
  - "IEnumDebugPorts2::Reset"
ms.assetid: 67da406c-eadb-421e-ae12-e26e9866f262
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugPorts2::Reset
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
 이 메서드 호출 후에 다음 호출을 [다음](../../../extensibility/debugger/reference/ienumdebugports2-next.md) 메서드 열거형의 첫 번째 요소를 반환 합니다.  
  
## 참고 항목  
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)