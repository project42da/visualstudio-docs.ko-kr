---
title: "IDebugMethodField::IsCustomAttributeDefined | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugMethodField::IsCustomAttributeDefined"
helpviewer_keywords: 
  - "IDebugMethodField::IsCustomAttributeDefined 메서드"
ms.assetid: 1b5d95a8-cc87-4acb-9e6a-3928f3632b7c
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugMethodField::IsCustomAttributeDefined
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

특정 사용자 지정 특성의 정의 여부를 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT IsCustomAttributeDefined(   
   LPCOLESTR pszCustomAttributeName  
);  
```  
  
```c#  
int IsCustomAttributeDefined(  
   [In] string pszCustomAttributeName  
);  
```  
  
#### 매개 변수  
 `pszCustomAttributeName`  
 \[in\] 찾기 사용자 지정 특성의 이름을 포함 하는 문자열입니다.  
  
## 반환 값  
 이 메서드를 사용자 지정 특성을 정의 하면 S\_OK 그렇지 않으면 S\_FALSE를 반환 하거나 반환 합니다.  
  
## 참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)