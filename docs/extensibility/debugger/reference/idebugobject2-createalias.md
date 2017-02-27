---
title: "IDebugObject2::CreateAlias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugObject2::CreateAlias"
helpviewer_keywords: 
  - "IDebugObject2::CreateAlias 메서드"
ms.assetid: 54a05920-5d13-4f67-962b-d1a7f013dff9
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugObject2::CreateAlias
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

고유 ID 또는이 개체에 대 한 별칭을 만듭니다 또는 기존 별칭을 반환 합니다.  
  
## 구문  
  
```cpp  
HRESULT CreateAlias(  
   IDebugAlias** ppAlias  
);  
```  
  
```c#  
int CreateAlias(  
   out IDebugAlias ppAlias  
);  
```  
  
#### 매개 변수  
 `ppAlias`  
 \[out\] \(기존 또는 새\) 별칭입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 별칭 개체는 메모리에 있는 동안 특정 개체를 나타내는 레이블이 있습니다.  
  
## 참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)