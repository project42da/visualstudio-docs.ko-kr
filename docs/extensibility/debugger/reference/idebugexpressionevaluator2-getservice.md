---
title: "IDebugExpressionEvaluator2::GetService | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugExpressionEvaluator2::GetService"
  - "GetService"
ms.assetid: f8988a9e-9d18-42af-84a7-55f41e9adf63
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugExpressionEvaluator2::GetService
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

고유 식별자를 제공 하는 서비스 개체를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetService (  
   GUID        uid,  
   IUnknown ** ppService  
);  
```  
  
```c#  
int GetService (  
   Guid       uid,  
   out object ppService  
);  
```  
  
#### 매개 변수  
 `uid`  
 \[in\] 검색할 서비스의 고유 식별자입니다.  
  
 `ppService`  
 \[out\] 서비스를 나타내는 개체를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 다른 식 계산기에서 서비스를 가져오는 데는 타사 식 계산기가 사용할 수 있습니다.  예를 들어, 기본 식 계산기에서 시각화 도우미 서비스에 대 한 인터페이스를 가져오려면이 메서드를 사용 수 있습니다.  제 3의 식 계산기가이 인터페이스를 구현 해야 하는 흔하지 않습니다.  
  
## 참고 항목  
 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)