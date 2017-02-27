---
title: "IDebugObject2::GetAlias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugObject2::GetAlias"
helpviewer_keywords: 
  - "IDebugObject2::GetAlias 메서드"
ms.assetid: aa6824d5-c932-42ba-8713-950e7d1fb42f
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugObject2::GetAlias
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 개체와 관련 된 별칭을 가져옵니다.  
  
## 구문  
  
```cpp  
HRESULT GetAlias(  
   IDebugAlias** ppAlias  
);  
```  
  
```c#  
int GetAlias(  
   out IDebugAlias ppAlias  
);  
```  
  
#### 매개 변수  
 `ppAlias`  
 \[out\] 반환 된 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) 개체 별칭 개체입니다. 그렇지 않으면 null 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 별칭 개체에 대 한 호출로 만들어진의 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) 메서드가 있습니다.  
  
## 참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)