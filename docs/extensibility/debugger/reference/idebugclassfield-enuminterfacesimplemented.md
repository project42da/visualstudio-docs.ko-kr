---
title: "IDebugClassField::EnumInterfacesImplemented | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugClassField::EnumInterfacesImplemented"
helpviewer_keywords: 
  - "IDebugClassField::EnumInterfacesImplemented 메서드"
ms.assetid: e5523e45-d350-491e-a92c-fe0ca97d2052
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugClassField::EnumInterfacesImplemented
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 클래스에 의해 구현 된 인터페이스에 대 한 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumInterfacesImplemented(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```c#  
int EnumInterfacesImplemented(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### 매개 변수  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 목록에 구현 되는 인터페이스를 나타내는 개체입니다.  인터페이스가 있을 경우 null 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 하거나이 클래스에서 구현 된 인터페이스가 없으면 S\_FALSE를 반환 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 각 요소는 열거형은 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 인터페이스를 설명 하는 개체입니다.  관리 되지 않는 참고 [!INCLUDE[vcprvc](../../../debugger/includes/vcprvc_md.md)] 코드 사용 하지 않는 인터페이스 분리 된 개체로이 메서드가 관리 되지 않는 대 한 null 값을 항상 반환 하므로 [!INCLUDE[vcprvc](../../../debugger/includes/vcprvc_md.md)] 코드입니다.  
  
## 참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)