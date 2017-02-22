---
title: "IDebugClassField::EnumBaseClasses | Microsoft Docs"
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
  - "IDebugClassField::EnumBaseClasses"
helpviewer_keywords: 
  - "IDebugClassField::EnumBaseClasses 메서드"
ms.assetid: 78749674-ef75-46d3-a1f4-ff33afd90e32
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugClassField::EnumBaseClasses
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 클래스의 기본 클래스에 대 한 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumBaseClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```c#  
int EnumBaseClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### 매개 변수  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 목록에 기본 클래스를 나타내는 개체입니다.  기본 클래스가 있는 경우 null 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 하 고 없음 기본 클래스 이면 S\_SH\_NO\_BASE\_CLASSES이 반환 \(와 `ppEnum` 매개 변수를 null 값으로 설정 됩니다\). 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 열거자 개체의 기본 클래스 순서 대로 가장 즉시 \(또는 가장 많이 파생 된\) 기본 클래스는 대부분의 원격 기본 클래스를 지정 합니다.  예를 들어, c \+ \+ 클래스를 가정합니다.  
  
```  
class Root { }  
class Level1 : Root { }  
class Level2 : Level1 { }  
class MyClass : Level2 { }  
```  
  
 열거 된 순서 대로 기본 클래스를 반환 합니다 `Level2`, `Level1`, `Root`.  
  
## 참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)