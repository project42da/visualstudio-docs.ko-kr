---
title: "IDebugObject2::GetICorDebugValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugObject2::GetICorDebugValue"
helpviewer_keywords: 
  - "IDebugObject2::GetICorDebugValue 메서드"
ms.assetid: bcd4355d-3fbe-483f-bb23-a44348323c6a
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugObject2::GetICorDebugValue
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 개체와 연결 된 값을 나타내는 코드를 관리 되는 개체를 가져옵니다.  
  
## 구문  
  
```cpp  
HRESULT GetICorDebugValue(  
   IUnknown** ppUnk  
);  
```  
  
```c#  
int GetICorDebugValue(  
   out object ppUnk  
);  
```  
  
#### 매개 변수  
 `ppUnk`  
 \[out\] `IUnknown` 이 별칭을 나타내는 인터페이스입니다.  이 인터페이스를 쿼리할 수 있는 `ICorDebugValue` 인터페이스입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 `ICorDebugValue` 개체는 값을 나타내는 공용 언어 런타임에서 인터페이스입니다.  
  
## 참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)