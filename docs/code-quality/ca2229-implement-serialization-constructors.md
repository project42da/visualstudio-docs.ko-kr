---
title: "CA2229: serialization 생성자를 구현하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2229"
  - "ImplementSerializationConstructors"
helpviewer_keywords: 
  - "CA2229"
  - "ImplementSerializationConstructors"
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 15
---
# CA2229: serialization 생성자를 구현하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ImplementSerializationConstructors|  
|CheckId|CA2229|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스를 구현하는 형식이 대리자나 인터페이스가 아니고 다음 조건 중 하나에 해당합니다.  
  
-   형식에 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> 개체 및 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> 개체\(serialization 생성자의 시그니처\)를 사용하는 생성자가 없는 경우  
  
-   형식이 unsealed이고 해당 serialization 생성자에 대한 액세스 한정자가 protected가 아닌 경우\(패밀리\)  
  
-   형식이 sealed이고 해당 serialization 생성자에 대한 액세스 한정자가 private이 아닌 경우  
  
## 규칙 설명  
 이 규칙은 사용자 지정 serialization을 지원하는 형식과 관련이 있습니다.  형식이 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현할 경우 이 형식은 사용자 지정 serialization을 지원합니다.  <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 메서드를 사용하여 serialize된 개체를 다시 만들거나 deserialize하려면 serialization 생성자가 필요합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 serialization 생성자를 구현합니다.  봉인 클래스의 경우에는 생성자를 private으로 만들고, 그 밖의 경우에는 protected로 만듭니다.  
  
## 경고를 표시하지 않는 경우  
 규칙 위반을 표시해야 합니다.  형식을 deserialize할 수 없으므로 많은 시나리오에서 동작하지 않게 됩니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 만족하는 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.ISerializableCtor#1](../code-quality/codesnippet/CSharp/ca2229-implement-serialization-constructors_1.cs)]  
  
## 관련 규칙  
 [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
## 참고 항목  
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>   
 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>