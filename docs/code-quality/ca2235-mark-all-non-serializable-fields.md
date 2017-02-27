---
title: "CA2235: 모두 serialize할 수 없는 필드로 표시하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2235"
  - "MarkAllNonSerializableFields"
helpviewer_keywords: 
  - "CA2235"
  - "MarkAllNonSerializableFields"
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 13
---
# CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MarkAllNonSerializableFields|  
|CheckId|CA2235|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 serialize할 수 없는 형식의 인스턴스 필드가 serialize할 수 있는 형식에 정의되었습니다.  
  
## 규칙 설명  
 serialize할 수 있는 형식은 <xref:System.SerializableAttribute?displayProperty=fullName> 특성으로 표시된 형식입니다.  형식이 serialize될 때 형식에 serialize할 수 없는 형식의 인스턴스 필드가 있으면 <xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> 예외가 throw됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 serialize할 수 없는 필드에 <xref:System.NonSerializedAttribute?displayProperty=fullName> 특성을 적용합니다.  
  
## 경고를 표시하지 않는 경우  
 필드의 인스턴스를 serialize 및 deserialize할 수 있도록 허용하는 <xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName> 형식이 선언된 경우에만 이 규칙에서 경고를 표시하지 않습니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식과 이 규칙을 충족하는 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/CSharp/ca2235-mark-all-non-serializable-fields_1.cs)]
 [!code-vb[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/VisualBasic/ca2235-mark-all-non-serializable-fields_1.vb)]  
  
## 관련 규칙  
 [CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: ISerializable을 올바르게 구현하십시오.](../Topic/CA2240:%20Implement%20ISerializable%20correctly.md)  
  
 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: serialization 메서드를 올바르게 구현하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
 [CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: serialization 생성자를 안전하게 하십시오.](../Topic/CA2120:%20Secure%20serialization%20constructors.md)