---
title: "CA2106: 어설션을 안전하게 하십시오. | Microsoft Docs"
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
  - "CA2106"
  - "SecureAsserts"
helpviewer_keywords: 
  - "CA2106"
  - "SecureAsserts"
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2106: 어설션을 안전하게 하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|SecureAsserts|  
|CheckId|CA2106|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 메서드에서 권한을 어설션하는데 호출자에 대해 보안 검사가 수행되지 않습니다.  
  
## 규칙 설명  
 보안 검사를 수행하지 않고 보안 권한을 어설션하면 코드에 보안상 취약한 부분이 남아 있을 수 있습니다.  보안 권한이 어설션되면 보안 스택 워크가 중단됩니다.  호출자에 대한 검사를 수행하지 않고 보안 권한을 어설션하면 호출자가 사용자 권한을 사용하여 간접적으로 코드를 실행할 수도 있습니다.  보안 검사 없는 어설션은 어설션이 유해한 방식으로 사용되지 않는다고 확신할 때만 허용됩니다.  사용자가 호출하는 어설션이 해가 없으면 어설션은 해가 없으며, 그렇지 않으면 사용자가 호출하는 코드에 임의의 정보를 전달할 수 없습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드 또는 선언 형식에 보안 요청을 추가합니다.  
  
## 경고를 표시하지 않는 경우  
 신중하게 보안을 검토한 후에만 이 규칙에서 경고를 표시하지 마십시오.  
  
## 참고 항목  
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>   
 [보안 코딩 지침](../Topic/Secure%20Coding%20Guidelines.md)