---
title: "IDebugClassField::GetEnclosingClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugClassField::GetEnclosingClass"
helpviewer_keywords: 
  - "IDebugClassField::GetEnclosingClass 메서드"
ms.assetid: a0c12e3c-9ea0-4dfb-9e45-8cea18725022
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugClassField::GetEnclosingClass
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 클래스를 포함 하는 클래스를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetEnclosingClass(   
   IDebugClassField** ppClassField  
);  
```  
  
```c#  
int GetEnclosingClass(  
   out IDebugClassField ppClassField  
);  
```  
  
#### 매개 변수  
 `ppClassField`  
 \[out\] 반환 된 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 개체 바깥쪽을 나타내는 클래스입니다.  바깥쪽 클래스가 없는 경우 null 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 클래스에서이 표시 하는 경우 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 개체는 중첩된 클래스를 다음의 `ppClassField` 매개 변수를 반환는 `IDebugClassField` 개체 바깥쪽을 나타내는 클래스입니다.  예를 들어,이 클래스 정의 가정합니다.  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 호출 하는 `GetEnclosingClass` 메서드를는 `IDebugClassField` 개체를 나타내는 `NestedClass` 반환 클래스는 `IDebugClassField` 개체 클래스를 나타내는 `RootClass`.  
  
## 참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)