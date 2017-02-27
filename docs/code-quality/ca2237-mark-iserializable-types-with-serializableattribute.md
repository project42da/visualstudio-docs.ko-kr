---
title: "CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2237"
  - "MarkISerializableTypesWithSerializable"
helpviewer_keywords: 
  - "CA2237"
  - "MarkISerializableTypesWithSerializable"
ms.assetid: 9bd6bb24-a527-43dd-9952-043c0c694f46
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 13
---
# CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MarkISerializableTypesWithSerializable|  
|CheckId|CA2237|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 외부에서 볼 수 있는 형식이 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스를 구현하고 이 형식이 <xref:System.SerializableAttribute?displayProperty=fullName> 특성으로 표시되어 있지 않습니다.  규칙에서는 기본 형식이 serializable이 아닌 파생 형식을 무시합니다.  
  
## 규칙 설명  
 공용 언어 런타임에서 serializable로 인식되도록 하려면 형식이 <xref:System.Runtime.Serialization.ISerializable> 인터페이스의 구현을 통해 사용자 지정 serialization 루틴을 사용하는 경우에도 형식을 <xref:System.SerializableAttribute> 특성으로 표시해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 형식에 <xref:System.SerializableAttribute> 특성을 적용합니다.  
  
## 경고를 표시하지 않는 경우  
 예외 클래스가 모든 응용 프로그램 도메인에서 제대로 작동하려면 serializable이어야 하므로 예외 클래스의 경우에는 이 규칙에서 경고를 표시하십시오.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 형식을 보여 줍니다.  규칙을 따르려면 <xref:System.SerializableAttribute> 특성의 주석 처리를 제거합니다.  
  
 [!code-vb[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/VisualBasic/ca2237-mark-iserializable-types-with-serializableattribute_1.vb)]
 [!code-cs[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/CSharp/ca2237-mark-iserializable-types-with-serializableattribute_1.cs)]  
  
## 관련 규칙  
 [CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: ISerializable을 올바르게 구현하십시오.](../Topic/CA2240:%20Implement%20ISerializable%20correctly.md)  
  
 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: serialization 메서드를 올바르게 구현하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
  
 [CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: serialization 생성자를 안전하게 하십시오.](../Topic/CA2120:%20Secure%20serialization%20constructors.md)