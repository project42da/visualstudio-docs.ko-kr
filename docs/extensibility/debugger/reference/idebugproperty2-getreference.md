---
title: "IDebugProperty2::GetReference | Microsoft Docs"
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
  - "IDebugProperty2::GetReference"
helpviewer_keywords: 
  - "IDebugProperty2::GetReference 메서드"
ms.assetid: 2fa97d9b-c3d7-478e-ba5a-a933f40a0103
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProperty2::GetReference
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

속성 값에 대 한 참조를 반환합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetReference(  
   IDebugReference2** ppReference  
);  
```  
  
```c#  
int GetReference(  
   out IDebugReference2 ppReference  
);  
```  
  
#### 매개 변수  
 `ppRererence`  
 \[out\] 반환 된 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 속성의 값에 대 한 참조를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드는 일반적으로 반환 `E_NOTIMPL` 또는 `E_GETREFERENCE_NO_REFERENCE`.  
  
## 참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)