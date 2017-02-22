---
title: "CA2109: 표시되는 이벤트 처리기를 검토하십시오. | Microsoft Docs"
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
  - "CA2109"
  - "ReviewVisibleEventHandlers"
helpviewer_keywords: 
  - "CA2109"
  - "ReviewVisibleEventHandlers"
ms.assetid: 8f8fa0ee-e94e-400e-b516-24d8727725d7
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2109: 표시되는 이벤트 처리기를 검토하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ReviewVisibleEventHandlers|  
|CheckId|CA2109|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 이벤트 처리 메서드를 발견했습니다.  
  
## 규칙 설명  
 외부에서 볼 수 있는 이벤트 처리 메서드는 보안 문제가 발생할 수 있으므로 검토가 필요합니다.  
  
 이벤트 처리 메서드는 반드시 필요한 경우를 제외하고 노출하면 안 됩니다.  노출된 메서드를 호출하는 대리자 형식인 이벤트 처리기는 처리기와 이벤트 시그니처가 일치하기만 하면 모든 이벤트에 추가될 수 있습니다.  이벤트는 모든 코드에서 발생할 수 있으며 신뢰 수준이 높은 시스템 코드에서 단추 클릭과 같은 사용자 작업에 대한 응답으로 자주 발생합니다.  이벤트 처리 메서드에 보안 검사를 추가해도 코드를 통해 메서드를 호출하는 이벤트 처리기의 등록을 막을 수 없습니다.  
  
 요청으로는 이벤트 처리기에서 호출하는 메서드를 안정적으로 보호할 수 없습니다.  보안 요청은 호출 스택에서 호출자를 검사함으로써 신뢰할 수 없는 호출자로부터 코드를 보호하는 데 도움이 됩니다.  이벤트 처리기의 메서드가 실행될 때 이벤트 처리기를 이벤트에 추가한 코드가 호출 스택에 반드시 존재하는 것은 아닙니다.  따라서 이벤트 처리기 메서드가 호출될 때 호출 스택에 신뢰 수준이 높은 호출자만 있을 수 있습니다.  이로 인해 이벤트 처리기에서 보낸 요청이 성공하게 됩니다.  또한 요청된 권한이 메서드가 호출될 때 어설션될 수도 있습니다.  이러한 이유로 이 규칙 위반 문제를 해결하지 않을 경우의 위험 수준은 이벤트 처리 메서드를 검토한 후에만 평가할 수 있습니다.  코드를 검토할 때 다음과 같은 문제를 고려하십시오.  
  
-   이벤트 처리기가 권한 어설션 또는 비관리 코드 권한 숨기기와 같은 위험하거나 악용될 가능성이 있는 작업을 수행하는지 여부  
  
-   스택에 신뢰 수준이 높은 호출자만 있을 때 언제든지 코드가 실행되어 발생할 수 있는 보안 위협  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드를 검토하고 다음을 평가합니다.  
  
-   이벤트 처리 메서드를 public이 아닌 메서드로 만들 수 있는지 여부  
  
-   위험한 기능을 모두 이벤트 처리기 외부로 이동할 수 있는지 여부  
  
-   보안 요청을 적용해야 하는 경우 다른 방식으로 수행할 수 있는지 여부  
  
## 경고를 표시하지 않는 경우  
 신중하게 보안 문제를 검토하여 코드에 보안 위험이 없음이 확인된 후에만 이 규칙에 따른 경고를 표시하지 마십시오.  
  
## 예제  
 다음 코드에서는 악의적인 코드를 통해 잘못 사용될 수 있는 이벤트 처리 메서드를 보여 줍니다.  
  
 [!code-cs[FxCop.Security.EventSecLib#1](../code-quality/codesnippet/CSharp/ca2109-review-visible-event-handlers_1.cs)]  
  
## 참고 항목  
 <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName>   
 <xref:System.EventArgs?displayProperty=fullName>   
 [Security Demands](http://msdn.microsoft.com/ko-kr/324c14f8-54ff-494d-9fd1-bfd20962c8ba)