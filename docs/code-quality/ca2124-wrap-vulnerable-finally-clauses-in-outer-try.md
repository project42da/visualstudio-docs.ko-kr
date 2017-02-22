---
title: "CA2124: 취약한 finally 절을 외부 try에 래핑하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2124"
  - "WrapVulnerableFinallyClausesInOuterTry"
helpviewer_keywords: 
  - "CA2124"
  - "WrapVulnerableFinallyClausesInOuterTry"
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2124: 취약한 finally 절을 외부 try에 래핑하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|WrapVulnerableFinallyClausesInOuterTry|  
|CheckId|CA2124|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 버전  1.0 및 1.1에서 public 또는 protected 메서드에 `try`\/`catch`\/`finally` 블록이 포함되어 있습니다.  `finally` 블록이 보안 상태를 다시 설정하고 `finally` 블록에 포함되지 않습니다.  
  
## 규칙 설명  
 이 규칙은 호출 스택에 있는 악의적인 예외 필터에 취약할 수 있는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 버전 1.0 및 1.1을 대상으로 하는 `try`\/`finally` 블록을 찾습니다.  try 블록에 가장과 같은 중요한 작업이 발생하면 예외가 throw되고 `finally` 블록 앞에서 필터가 실행될 수 있습니다.  가장을 예로 들면, 필터가 가장 사용자로 실행될 수 있다는 의미입니다.  필터는 현재 Visual Basic에서만 구현할 수 있습니다.  
  
> [!WARNING]
>  **참고**  [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 버전 2.0 이상에서 예외 블록이 포함된 메서드 내에서 다시 설정이 직접 발생하는 경우 런타임은 악의적인 예외 필터로부터 `try`\/`catch`\/ `finally` 블록을 자동으로 보호합니다.  
  
## 위반 문제를 해결하는 방법  
 래핑되지 않은 `try`\/`finally`를 외부 try 블록에 배치합니다.  다음 두 번째 예제를 참조하십시오.  이렇게 하면 필터 코드 앞에서 `finally`가 실행됩니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 의사\(pseudo\) 코드 예제  
  
### 설명  
 다음 의사\(pseudo\) 코드에서는 이 규칙을 통해 감지되는 패턴을 보여 줍니다.  
  
### 코드  
  
```  
try {  
   // Do some work.  
   Impersonator imp = new Impersonator("John Doe");  
   imp.AddToCreditCardBalance(100);  
}  
finally {  
   // Reset security state.  
   imp.Revert();  
}  
```  
  
## 예제  
 다음 의사\(pseudo\) 코드에서는 코드를 보호하고 이 규칙을 만족시키는 데 사용할 수 있는 패턴을 보여 줍니다.  
  
```  
try {  
     try {  
        // Do some work.  
     }  
     finally {  
        // Reset security state.  
     }  
}  
catch()  
{  
    throw;  
}  
```