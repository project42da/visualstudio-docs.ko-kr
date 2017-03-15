---
title: "IDebugExpressionEvaluator::SetRegistryRoot | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpressionEvaluator::SetRegistryRoot"
helpviewer_keywords: 
  - "IDebugExpressionEvaluator::SetRegistryRoot 메서드"
ms.assetid: 790886d8-1975-4d3c-9a75-cd86c1faf4ca
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugExpressionEvaluator::SetRegistryRoot
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 레지스트리 루트를 설정합니다.  병렬 디버깅을 사용 합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetRegistryRoot (   
   LPCOLESTR ustrRegistryRoot  
);  
```  
  
```c#  
int SetRegistryRoot(  
   string ustrRegistryRoot  
);  
```  
  
#### 매개 변수  
 `ustrRegistryRoot`  
 \[in\] 새 레지스트리 루트입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 지정 된 레지스트리 루트는 식 계산기 처음 인스턴스화될 때 가리키는 일반적으로 설정 됩니다 Visual Studio 특정 버전에 대 한 레지스트리 키 \(HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*X.Y*, 어디  *X.Y* 버전 번호입니다\)입니다.  
  
## 참고 항목  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)