---
title: "IDebugAlias::GetObject | Microsoft Docs"
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
  - "IDebugAlias::GetObject"
helpviewer_keywords: 
  - "IDebugAlias::GetObject 메서드"
ms.assetid: 97bc3af6-6e55-4940-8a6d-692c61257806
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugAlias::GetObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 별칭에 대 한 개체를 가져옵니다.  
  
## 구문  
  
```cpp  
HRESULT GetObject(  
   IDebugObject2** ppObject  
);  
```  
  
```c#  
int GetObject(  
   Out IDebugObject2 ppObject  
)  
```  
  
#### 매개 변수  
 `ppObject`  
 \[out\] [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) 이 별칭을 나타냅니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)   
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)