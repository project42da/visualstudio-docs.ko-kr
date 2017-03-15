---
title: "CA1048: 가상 멤버를 sealed 형식으로 선언하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DoNotDeclareVirtualMembersInSealedTypes"
  - "CA1048"
helpviewer_keywords: 
  - "CA1048"
  - "DoNotDeclareVirtualMembersInSealedTypes"
ms.assetid: 5dcf4a30-6f98-48a8-b8cc-7b89ea757262
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 13
---
# CA1048: 가상 멤버를 sealed 형식으로 선언하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotDeclareVirtualMembersInSealedTypes|  
|CheckId|CA1048|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 형식이 sealed이며 `virtual`\(Visual Basic의 경우 `Overridable`\)이면서 final이 아닌 메서드를 선언합니다.  이 규칙은 이 패턴을 따라야 하는 대리자 형식에 대해서는 위반을 보고하지 않습니다.  
  
## 규칙 설명  
 상속 형식이 가상 메서드의 구현을 재정의할 수 있도록 하기 위해 형식은 메서드를 가상으로 선언합니다.  정의에 따르면 sealed 형식에서는 상속할 수 없으므로 sealed 형식에 가상 메서드를 만드는 것은 의미가 없습니다.  
  
 Visual Basic .NET 및 C\# 컴파일러에서는 형식이 이 규칙을 위반하지 못하도록 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드를 가상이 아닌 메서드로 만들거나 형식을 상속 가능한 형식으로 만듭니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  형식을 현재 상태로 그대로 두면 유지 관리 문제가 발생하므로 바람직하지 않습니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식을 보여 줍니다.  
  
 [!code-cpp[FxCop.Design.SealedVirtual#1](../code-quality/codesnippet/CPP/ca1048-do-not-declare-virtual-members-in-sealed-types_1.cpp)]