---
title: "IDebugExpressionContext2::GetName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpressionContext2::GetName"
helpviewer_keywords: 
  - "IDebugExpressionContext2::GetName"
ms.assetid: c2b70d22-17af-4986-a7e3-930910367216
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugExpressionContext2::GetName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

평가 컨텍스트 이름을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetName(   
   BSTR* pbstrName  
);  
```  
  
```c#  
int GetName(   
   out string pbstrName  
);  
```  
  
#### 매개 변수  
 `pbstrName`  
 \[out\] 평가 컨텍스트 이름을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이름이 평가 상황에 대 한 설명입니다.  일반적으로 것이 정확한 평가를 나타냅니다 식 계산기 구문 분석 될 수 있습니다.  예를 들어, c \+ \+에서는 다음과 같은 이름이입니다.  
  
```  
"{ function-name, source-file-name, module-file-name }"  
```  
  
## 참고 항목  
 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)