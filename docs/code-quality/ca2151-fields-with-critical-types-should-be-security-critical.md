---
title: "CA2151: 중요한 형식이 포함된 필드는 보안에 중요한 필드여야 함 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09db9d25-7d58-4725-a252-4a07baadf046
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2151: 중요한 형식이 포함된 필드는 보안에 중요한 필드여야 함
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName||  
|CheckId|CA2151|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 보안 투명 필드 또는 안전 중요 필드가 선언되었습니다.  해당 형식은 보안에 중요한 것으로 지정되었습니다.  예를 들면 다음과 같습니다.  
  
```c#  
[assembly: AllowPartiallyTrustedCallers]  
  
   [SecurityCritical]  
   class Type1 { } // Security Critical type  
  
   class Type2 // Security transparent type  
   {  
      Type1 m_field; // CA2151, transparent field of critical type  
   }  
  
```  
  
 이 예제에서 `m_field`는 보안 중요 형식의 보안 투명 필드입니다.  
  
## 규칙 설명  
 보안 중요 형식을 사용하려면 이 형식을 참조하는 코드가 보안 중요 또는 보안 안전 중요여야 합니다.  참조가 간접적인 경우에도 마찬가지입니다.  예를 들어, 중요 형식이 있는 투명 필드를 참조할 경우 코드는 보안 중요 또는 보안 안전이어야 합니다.  따라서 투명 코드는 필드에 액세스할 수 없으므로 보안 투명 또는 보안 안전 중요 필드가 있을 경우 잘못 해석됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반을 해결하려면 필드에 <xref:System.Security.SecurityCriticalAttribute> 특성을 표시하거나 보안 투명 또는 안전 중요 필드가 참조하는 형식을 만듭니다.  
  
```c#  
// Fix 1: Make the referencing field security critical  
[assembly: AllowPartiallyTrustedCallers]  
  
   [SecurityCritical]  
   class Type1 { } // Security Critical type  
  
   class Type2 // Security transparent type  
   {  
      [SecurityCritical]  
      Type1 m_field; // Fixed: critical type, critical field  
   }  
  
// Fix 2: Make the referencing field security critical  
[assembly: AllowPartiallyTrustedCallers]  
  
   class Type1 { } // Type1 is now transparent  
  
   class Type2 // Security transparent type  
   {  
      [SecurityCritical]  
      Type1 m_field; // Fixed: critical type, critical field  
   }  
  
```  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
### 코드  
 [!code-cs[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2151-fields-with-critical-types-should-be-security-critical_1.cs)]  
  
### 설명