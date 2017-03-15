---
title: "CA2220: 종료자는 기본 클래스 종료자를 호출해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2220"
  - "FinalizersShouldCallBaseClassFinalizer"
helpviewer_keywords: 
  - "CA2220"
  - "FinalizersShouldCallBaseClassFinalizer"
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2220: 종료자는 기본 클래스 종료자를 호출해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|FinalizersShouldCallBaseClassFinalizer|  
|CheckId|CA2220|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 <xref:System.Object.Finalize%2A?displayProperty=fullName>를 재정의하는 형식이 기본 클래스의 <xref:System.Object.Finalize%2A> 메서드를 호출하지 않습니다.  
  
## 규칙 설명  
 종료는 상속 계층을 통해 전파되어야 합니다.  이를 위해 형식은 자체 <xref:System.Object.Finalize%2A> 메서드 내에서 기본 클래스의 <xref:System.Object.Finalize%2A> 메서드를 호출해야 합니다.  C\# 컴파일러에서는 기본 클래스 종료자에 대한 호출을 자동으로 추가합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 현재 <xref:System.Object.Finalize%2A> 메서드에서 기본 형식의 <xref:System.Object.Finalize%2A> 메서드를 호출합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  공용 언어 런타임을 대상으로 하는 일부 컴파일러에서는 기본 형식의 종결자에 대한 호출을 MSIL\(Microsoft intermediate language\)에 삽입합니다.  이 규칙의 경고가 보고되면 컴파일러에서 호출을 삽입하지 않으므로 사용자가 코드에 직접 호출을 삽입해야 합니다.  
  
## 예제  
 다음 Visual Basic 예제에서는 기본 클래스의 <xref:System.Object.Finalize%2A> 메서드를 올바르게 호출하는 `TypeB` 형식을 보여 줍니다.  
  
 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2220-finalizers-should-call-base-class-finalizer_1.vb)]  
  
## 참고 항목  
 [삭제 패턴](../Topic/Dispose%20Pattern.md)