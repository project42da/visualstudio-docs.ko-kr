---
title: "CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오. | Microsoft Docs"
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
  - "AvoidUncalledPrivateCode"
  - "CA1811"
helpviewer_keywords: 
  - "CA1811"
  - "AvoidUncalledPrivateCode"
ms.assetid: aadbba74-7821-475f-8980-34d17c0a0a8b
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidUncalledPrivateCode|  
|CheckId|CA1811|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 어셈블리에 전용 또는 내부\(어셈블리 수준\) 멤버의 호출자가 없고, 공용 언어 런타임에서도 이 멤버를 호출하지 않으며, 대리자에서도 이 멤버를 호출하지 않습니다.  이 규칙에서 다음 멤버는 확인하지 않습니다.  
  
-   명시적 인터페이스 멤버  
  
-   정적 생성자  
  
-   serialization 생성자  
  
-   <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> 또는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>로 표시된 메서드  
  
-   재정의 멤버  
  
## 규칙 설명  
 이 규칙에서는 규칙 논리에서 현재 식별할 수 없는 진입점이 있을 경우 가양성\(false positives\)을 보고할 수 있습니다.  또한 컴파일러는 noncallable 코드를 어셈블리로 내보낼 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 호출되지 않는 코드를 제거하거나 이를 호출하는 코드를 추가합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시하지 않아도 안전합니다.  
  
## 관련 규칙  
 [CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마십시오.](../Topic/CA1812:%20Avoid%20uninstantiated%20internal%20classes.md)  
  
 [CA1801: 사용되지 않은 매개 변수를 검토하십시오.](../Topic/CA1801:%20Review%20unused%20parameters.md)  
  
 [CA1804: 사용되지 않는 로컬 항목을 제거하십시오.](../code-quality/ca1804-remove-unused-locals.md)