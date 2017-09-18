---
title: "IDebugClassField::EnumNestedEnums | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugClassField::EnumNestedEnums"
helpviewer_keywords: 
  - "IDebugClassField::EnumNestedEnums 메서드"
ms.assetid: 90fd0cef-9145-4de6-91d4-6c881df39d6e
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugClassField::EnumNestedEnums
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 클래스의 중첩 된 열거자에 대 한 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumNestedEnums(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```c#  
int EnumNestedEnums(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### 매개 변수  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 목록을 중첩 된 열거형을 나타내는 개체입니다.  중첩된 열거형 없는 경우 null 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 하거나 없는 중첩된 열거자 없으면 S\_FALSE를 반환 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 열거형의 각 요소는 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) 는 중첩 된 열거형을 설명 하는 개체입니다.  
  
 열거형을 클래스 내에 선언 된 중첩 된 열거형으로 간주 됩니다.  예를 들면, 다음과 같습니다.  
  
```  
class RootClass {  
   enum NestedEnum { EnumValue = 0 }  
};  
```  
  
 `EnumNestedEnums` 메서드 반환은 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 하나를 포함 하는 개체 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) 나타내는 개체는 `NestedEnum` 열거형입니다.  
  
## 참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)