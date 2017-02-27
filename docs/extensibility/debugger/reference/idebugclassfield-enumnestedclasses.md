---
title: "IDebugClassField::EnumNestedClasses | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugClassField::EnumNestedClasses"
helpviewer_keywords: 
  - "IDebugClassField::EnumNestedClasses 메서드"
ms.assetid: 2ba5ef0c-395e-4006-9e3c-9b06e1d711d0
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugClassField::EnumNestedClasses
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 클래스에서 중첩 된 클래스에 대 한 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumNestedClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```c#  
int EnumNestedClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### 매개 변수  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 목록에 중첩 된 클래스를 나타내는 개체입니다.  중첩 된 클래스가 있는 경우 null 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 하거나 중첩된 클래스가 없으면 S\_FALSE를 반환 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 열거형의 각 요소는 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 중첩 된 클래스를 설명 하는 개체입니다.  
  
 중첩된 클래스는 다른 클래스 내에 정의 된 클래스가입니다.  예를 들면 다음과 같습니다.  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 열거형 개체 하나를 나타내는 포함 됩니다 있는 `NestedClass` 클래스입니다.  
  
## 참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)