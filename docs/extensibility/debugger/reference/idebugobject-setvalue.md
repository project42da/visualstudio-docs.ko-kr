---
title: "IDebugObject::SetValue | Microsoft Docs"
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
  - "IDebugObject::SetValue"
helpviewer_keywords: 
  - "IDebugObject::SetValue 메서드"
ms.assetid: d652e09c-cdc1-4519-8116-d7c743f5679b
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugObject::SetValue
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

연속 된 일련의 바이트에서 개체의 값을 설정합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetValue(   
   BYTE* pValue,  
   UINT  nSize  
);  
```  
  
```c#  
int SetValue(  
   byte[] pValue,   
   uint   nSize  
);  
```  
  
#### 매개 변수  
 `pValue`  
 \[in\] 새 값을 나타내는 바이트 배열입니다.  
  
 `nSize`  
 \[in\] 크기 값 \(바이트\)에서입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 배열에 값이 복사 됩니다 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체에서 기존 값을 대체 합니다.  크기를 새 값 기존 값 보다 크거나 작을 수 있습니다.  이 `IDebugObject` 는 null 참조 여야 합니다.  
  
## 참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)