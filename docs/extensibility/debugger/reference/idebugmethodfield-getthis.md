---
title: "IDebugMethodField::GetThis | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugMethodField::GetThis"
helpviewer_keywords: 
  - "IDebugMethodField::GetThis 메서드"
ms.assetid: cc235bea-e909-4d8c-ab54-936736c803fc
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugMethodField::GetThis
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

가져옵니다는 `this` \(`Me` 에서 [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]\) 포인터 메서드를 포함 하는 개체입니다.  
  
## 구문  
  
```cpp#  
HRESULT GetThis(   
   IDebugClassField** ppClass  
);  
```  
  
```c#  
int GetThis(  
   out IDebugClassField ppClass  
);  
```  
  
#### 매개 변수  
 `ppClass`  
 \[out\] 반환 된 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) "this"이 포인터를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 개체 지향 언어에서 클래스의 현재 인스턴스는 암시적된 포인터는 일반적으로 합니다.  This is known as `this` in C\#\/C\+\+ and as `Me` in [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)].  
  
## 참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)