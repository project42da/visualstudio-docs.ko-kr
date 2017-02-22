---
title: "IDebugObject::SetReferenceValue | Microsoft Docs"
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
  - "IDebugObject::SetReferenceValue"
helpviewer_keywords: 
  - "IDebugObject::SetReferenceValue 메서드"
ms.assetid: 08c78a4e-98eb-41cb-8b75-02a6a43d49f7
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugObject::SetReferenceValue
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 개체의 참조 값을 설정합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetReferenceValue(   
   IDebugObject* pObject  
);  
```  
  
```c#  
int SetReferenceValue(  
   [In] IDebugObject pObject  
);  
```  
  
#### 매개 변수  
 `pObject`  
 \[in\] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 새 참조 값을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는이 있습니다 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체 지정 된 개체의 값에 대 한 참조는 `pObject` 떨어져 모든 이전 참조를 throw 하는 매개 변수입니다.  참고가 `IDebugObject` 개체 참조 형식이 이미 있어야 합니다.  
  
## 참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)