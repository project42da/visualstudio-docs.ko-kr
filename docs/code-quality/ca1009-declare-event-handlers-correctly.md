---
title: "CA1009: 이벤트 처리기를 제대로 선언하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1009"
  - "DeclareEventHandlersCorrectly"
helpviewer_keywords: 
  - "CA1009"
  - "DeclareEventHandlersCorrectly"
ms.assetid: ab65c471-1449-49d2-9896-7b9af74284b4
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1009: 이벤트 처리기를 제대로 선언하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DeclareEventHandlersCorrectly|  
|CheckId|CA1009|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 이벤트를 처리하는 대리자에 올바른 시그니처, 반환 형식 또는 매개 변수 이름이 없습니다.  
  
## 규칙 설명  
 이벤트 처리기 메서드는 두 개의 매개 변수를 사용합니다.  첫 번째 매개 변수는 <xref:System.Object?displayProperty=fullName> 형식이고 이름은 'sender'입니다.  이 매개 변수는 이벤트를 발생시킨 개체입니다.  두 번째 매개 변수는 <xref:System.EventArgs?displayProperty=fullName> 형식이고 이름은 'e'입니다.  이 매개 변수는 이벤트와 관련된 데이터입니다.  예를 들어, 파일을 열 때마다 이벤트가 발생하면 이벤트 데이터에는 대개 파일 이름이 포함됩니다.  
  
 이벤트 처리기 메서드는 값을 반환하면 안 됩니다.  C\# 프로그래밍 언어에서는 반환 값 `void`로 이를 나타냅니다.  이벤트 처리기는 여러 개체의 여러 메서드를 호출할 수 있습니다.  이들 메서드가 값을 반환할 수 있으면 각 이벤트에 여러 개의 반환 값이 발생하게 되고 마지막으로 호출된 메서드의 값만 사용할 수 있게 됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 대리자의 시그니처, 반환 형식 또는 매개 변수 이름을 올바로 수정합니다.  자세한 내용은 다음 예제를 참조하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이벤트를 처리하는 데 적합한 대리자를 보여 줍니다.  디자인 지침에 지정된 시그니처를 따르도록 이 이벤트 처리기에서 호출할 수 있는 메서드입니다.  `AlarmEventHandler`는 대리자의 형식 이름입니다.  `AlarmEventArgs`는 이벤트 데이터의 기본 클래스인 <xref:System.EventArgs>에서 파생되며 경고 이벤트 데이터를 보유합니다.  
  
 [!code-cpp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CPP/ca1009-declare-event-handlers-correctly_1.cpp)]
 [!code-cs[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CSharp/ca1009-declare-event-handlers-correctly_1.cs)]
 [!code-vb[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/VisualBasic/ca1009-declare-event-handlers-correctly_1.vb)]  
  
## 관련 규칙  
 [CA2109: 표시되는 이벤트 처리기를 검토하십시오.](../code-quality/ca2109-review-visible-event-handlers.md)  
  
## 참고 항목  
 <xref:System.EventArgs?displayProperty=fullName>   
 <xref:System.Object?displayProperty=fullName>   
 [이벤트 및 대리자](http://msdn.microsoft.com/ko-kr/d98fd58b-fa4f-4598-8378-addf4355a115)