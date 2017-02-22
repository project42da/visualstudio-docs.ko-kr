---
title: "IDebugExpressionEvaluator::SetLocale | Microsoft Docs"
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
  - "IDebugExpressionEvaluator::SetLocale"
helpviewer_keywords: 
  - "IDebugExpressionEvaluator::SetLocale 메서드"
ms.assetid: d3d2027d-74e2-4ae6-bcc7-59d12f873b7c
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugExpressionEvaluator::SetLocale
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 방법을 볼 수 있는 결과 만드는 데 사용 하는 언어를 설정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetLocale(   
   WORD wLangID  
);  
```  
  
```c#  
int SetLocale(  
   ushort wLangID  
);  
```  
  
#### 매개 변수  
 `wLangID`  
 \[in\] 언어 식별자입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 EE를 즉석에서 언어를 전환할 수 있어야 하므로 식 계산기 \(EE\) 로드 되는 동안이 메서드를 여러 번 호출할 수 있습니다.  EE이이 로케일을 사용 하 여 해당 언어로 오류 메시지 및 문자열을 반환 합니다.  
  
## 참고 항목  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)