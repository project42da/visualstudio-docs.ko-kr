---
title: "IDebugCustomAttribute::GetParentField | Microsoft Docs"
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
  - "IDebugCustomAttribute::GetParentField"
helpviewer_keywords: 
  - "IDebugCustomAttribute::GetParentField"
ms.assetid: bcdfdf37-bfcf-4988-a7b8-4c731d0af1b0
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCustomAttribute::GetParentField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 지정 특성에 연결 된 필드를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetParentField(   
   IDebugField** ppField  
);  
```  
  
```c#  
int GetParentField(  
   out IDebugField ppField  
);  
```  
  
#### 매개 변수  
 `ppField`  
 \[out\] 반환은 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 사용자 지정 특성 첨부 된 필드를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 호출 하는 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 메서드에서 반환 되는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 어떤 종류의 부모 필드를 결정 하는 개체입니다.  
  
## 참고 항목  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)