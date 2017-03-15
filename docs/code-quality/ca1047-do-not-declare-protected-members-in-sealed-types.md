---
title: "CA1047: protected 멤버를 sealed 형식으로 선언하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DoNotDeclareProtectedMembersInSealedTypes"
  - "CA1047"
helpviewer_keywords: 
  - "CA1047"
  - "DoNotDeclareProtectedMembersInSealedTypes"
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 16
---
# CA1047: protected 멤버를 sealed 형식으로 선언하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|  
|CheckId|CA1047|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 public 형식이 `sealed`\(Visual Basic의 경우 `NotInheritable`\)이면서 보호된 멤버나 보호된 중첩 형식을 선언합니다.  이 규칙은 이 패턴을 따라야 하는 <xref:System.Object.Finalize%2A> 메서드에 대해서는 위반을 보고하지 않습니다.  
  
## 규칙 설명  
 형식에서는 상속하는 형식에서 멤버에 액세스하거나 멤버를 재정의할 수 있도록 하기 위해 protected 멤버를 선언합니다.  정의에 따르면 sealed 형식에서는 상속할 수 없습니다. 이것은 sealed 형식에 대해 protected 메서드를 호출할 수 없다는 의미입니다.  
  
 C\# 컴파일러에서는 이 오류에 대해 경고를 발생시킵니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 멤버의 액세스 수준을 private으로 변경하거나 형식을 상속 가능하도록 만듭니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  형식을 현재 상태로 그대로 두면 유지 관리 문제가 발생하므로 바람직하지 않습니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식을 보여 줍니다.  
  
 [!code-vb[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/VisualBasic/ca1047-do-not-declare-protected-members-in-sealed-types_1.vb)]
 [!code-cs[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/CSharp/ca1047-do-not-declare-protected-members-in-sealed-types_1.cs)]