---
title: "IDebugCustomAttribute::GetAttributeTypeField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCustomAttribute::GetAttributeTypeField"
helpviewer_keywords: 
  - "IDebugCustomAttribute::GetAttributeTypeField"
ms.assetid: d6ce26d5-42ba-44c1-8659-0516db5bc82d
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugCustomAttribute::GetAttributeTypeField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 지정 특성 클래스 형식을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetAttributeTypeField(   
   IDebugClassField** ppCAType  
);  
```  
  
```c#  
int GetAttributeTypeField(  
   out IDebugClassField ppCAType  
);  
```  
  
#### 매개 변수  
 `ppCAType`  
 \[out\] 반환은 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 사용자 지정 특성의 인스턴스를 포함 된 클래스를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 사용자 지정 특성 클래스를 항상입니다.  이 메서드에 액세스할 수는 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 해당 클래스에 설명 하는 개체입니다.  
  
## 참고 항목  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)   
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)