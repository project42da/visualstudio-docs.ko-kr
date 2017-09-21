---
title: "IDebugMethodField::GetGlobalContainer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugMethodField::GetGlobalContainer"
helpviewer_keywords: 
  - "IDebugMethodField::GetGlobalContainer 메서드"
ms.assetid: 041ac5aa-0b80-4310-b9ae-b88f8e7e0e5f
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugMethodField::GetGlobalContainer
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

전역 컨테이너를 메서드를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetGlobalContainer(  
   IDebugClassField** ppClass  
);  
```  
  
```c#  
int GetGlobalContainer(  
   out IDebugClassField ppClass  
);  
```  
  
#### 매개 변수  
 `ppClass`  
 \[out\] 반환 된 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 이 메서드에 정의 된 모듈을 나타내는.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 반환 되는 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 개체 전체 모듈을 나타내며 인공 개체입니다, 즉, 모듈 자체는 실제 클래스 하지는 않지만 표현 하 여는 `IDebugClassField` 개체를 열거 하 고 검색 하는 모듈의 다양 한 요소입니다.  
  
## 참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)