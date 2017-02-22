---
title: "CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오. | Microsoft Docs"
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
  - "CA2236"
  - "CallBaseClassMethodsOnISerializableTypes"
helpviewer_keywords: 
  - "CA2236"
  - "CallBaseClassMethodsOnISerializableTypes"
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|CallBaseClassMethodsOnISerializableTypes|  
|CheckId|CA2236|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 형식이 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스를 구현하는 형식에서 파생되고 다음 조건 중 하나에 해당합니다.  
  
-   형식이 serialization 생성자 즉, <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>, <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> 매개 변수 시그너처가 있는 생성자를 구현하지만 기본 형식의 serialization 생성자를 호출하지 않습니다.  
  
-   형식이 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 메서드를 구현하지만 기본 형식의 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드를 호출하지 않습니다.  
  
## 규칙 설명  
 사용자 지정 serialization 프로세스에서 형식은 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드를 구현하여 필드를 serialize하고 serialization 생성자를 구현하여 필드를 deserialize합니다.  형식이 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현하는 형식에서 파생되는 경우 기본 형식의 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드 및 serialization 생성자를 호출하여 기본 형식의 필드를 serialize 및 deserialize해야 합니다.  이렇게 하지 않으면 형식이 올바르게 serialize 및 deserialize되지 않습니다.  파생된 형식이 새로운 필드를 추가하지 않는 경우 형식은 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드 또는 serialization 생성자를 구현하거나 이에 해당하는 기본 형식의 요소를 호출할 필요가 없습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 해당하는 파생된 형식의 메서드나 생성자에서 기본 형식의 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드나 serialization 생성자를 호출합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 기본 클래스의 serialization 생성자와 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드를 호출하여 규칙을 충족하는 파생된 형식을 보여 줍니다.  
  
 [!code-vb[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/VisualBasic/ca2236-call-base-class-methods-on-iserializable-types_1.vb)]
 [!code-cs[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/CSharp/ca2236-call-base-class-methods-on-iserializable-types_1.cs)]  
  
## 관련 규칙  
 [CA2240: ISerializable을 올바르게 구현하십시오.](../Topic/CA2240:%20Implement%20ISerializable%20correctly.md)  
  
 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: serialization 메서드를 올바르게 구현하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
  
 [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
 [CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: serialization 생성자를 안전하게 하십시오.](../Topic/CA2120:%20Secure%20serialization%20constructors.md)