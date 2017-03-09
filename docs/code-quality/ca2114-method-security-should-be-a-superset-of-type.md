---
title: "CA2114: 메서드 보안은 형식의 상위 집합이어야 합니다. | Microsoft Docs"
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
  - "MethodSecurityShouldBeASupersetOfType"
  - "CA2114"
helpviewer_keywords: 
  - "CA2114"
  - "MethodSecurityShouldBeASupersetOfType"
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2114: 메서드 보안은 형식의 상위 집합이어야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MethodSecurityShouldBeASupersetOfType|  
|CheckId|CA2114|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 형식에 선언적 보안이 있으며 이 형식의 메서드 중 하나에 같은 보안 동작에 대한 선언적 보안이 있고, 보안 동작이 [링크 요청](../Topic/Link%20Demands.md) 또는 [Inheritance Demands](http://msdn.microsoft.com/ko-kr/28b9adbb-8f08-4f10-b856-dbf59eb932d9)가 아니며, 형식에서 검사하는 권한이 메서드에서 검사하는 권한의 하위 집합이 아닙니다.  
  
## 규칙 설명  
 메서드에는 같은 동작에 대해 메서드 수준과 형식 수준의 선언적 보안이 모두 있으면 안 됩니다.  두 검사는 조합되지 않으며 메서드 수준 요청만 적용됩니다.  예를 들어, 형식에서 `X` 권한을 요청하고 이 형식의 메서드 중 하나에서 `Y` 권한을 요청하는 경우 코드에서는 `X` 권한이 없어도 메서드를 실행할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 코드를 검토하여 두 동작이 모두 필요한지 확인합니다.  두 동작이 모두 필요한 경우 메서드 수준 동작에 형식 수준에서 지정된 보안이 포함되는지 확인합니다.  예를 들어, 형식에서 `X` 권한을 요청하고 해당 형식의 메서드도 `Y` 권한을 요청해야 하는 경우 메서드는 `X`와 `Y`를 명시적으로 요청해야 합니다.  
  
## 경고를 표시하지 않는 경우  
 형식에서 지정한 보안이 메서드에 필요하지 않은 경우 이 규칙에서 경고를 표시하지 않아도 안전합니다.  그러나 이러한 경우는 일반적이지 않으므로 디자인을 신중하게 검토해야 합니다.  
  
## 예제  
 다음 예제에서는 환경 권한을 사용하여 이 규칙을 위반할 경우의 위험성을 보여 줍니다.  이 예제의 응용 프로그램 코드에서는 형식에서 요구하는 권한을 거부하기 전에 보안된 형식의 인스턴스를 만듭니다.  실제의 위협 시나리오에서는 응용 프로그램에서 개체의 인스턴스를 가져올 수 있는 다른 방법이 필요합니다.  
  
 다음 예제에서는 라이브러리가 형식에 대한 쓰기 권한과 메서드에 대한 읽기 권한을 요청합니다.  
  
 [!code-cs[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]  
  
## 예제  
 다음 응용 프로그램 코드에서는 형식 수준 보안 요구 사항에는 맞지 않지만 메서드를 호출하여 라이브러리의 취약성을 보여 줍니다.  
  
 [!code-cs[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **\[모든 권한\] 개인 정보: 6\/16\/1964 12:00:00 AM**  
**\[쓰기 권한이 없음\(형식에서 요구\)\] 개인 정보: 6\/16\/1964 12:00:00 AM**  
**\[읽기 권한 없음\(메서드에서 요구\)\] 개인 정보에 액세스할 수 없습니다: 요청에 실패했습니다.**   
## 참고 항목  
 [보안 코딩 지침](../Topic/Secure%20Coding%20Guidelines.md)   
 [Inheritance Demands](http://msdn.microsoft.com/ko-kr/28b9adbb-8f08-4f10-b856-dbf59eb932d9)   
 [링크 요청](../Topic/Link%20Demands.md)   
 [데이터 및 모델링](../Topic/Data%20and%20Modeling%20in%20the%20.NET%20Framework.md)