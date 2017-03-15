---
title: "CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2239"
  - "ProvideDeserializationMethodsForOptionalFields"
helpviewer_keywords: 
  - "CA2239"
  - "ProvideDeserializationMethodsForOptionalFields"
ms.assetid: 6480ff5e-0caa-4707-814e-2f927cdafef5
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 13
---
# CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ProvideDeserializationMethodsForOptionalFields|  
|CheckId|CA2239|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 형식에 <xref:System.Runtime.Serialization.OptionalFieldAttribute?displayProperty=fullName> 특성으로 표시된 필드가 있으며 형식에서 deserialization 이벤트 처리 메서드를 제공하지 않습니다.  
  
## 규칙 설명  
 <xref:System.Runtime.Serialization.OptionalFieldAttribute> 특성은 serialization에 영향을 주지 않습니다. 이 특성으로 표시된 필드는 serialize됩니다.  하지만 deserialization에서는 이 필드가 무시되어 해당 형식과 연관된 기본값을 유지합니다.  deserialization 프로세스 도중 필드를 설정하려면 deserialization 이벤트 처리기를 선언해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 형식에 deserialization 이벤트 처리 메서드를 추가합니다.  
  
## 경고를 표시하지 않는 경우  
 deserialization 프로세스 도중 필드를 무시해야 하는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 선택적 필드와 deserialization 이벤트 처리 메서드가 있는 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/CSharp/ca2239-provide-deserialization-methods-for-optional-fields_1.cs)]
 [!code-vb[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/VisualBasic/ca2239-provide-deserialization-methods-for-optional-fields_1.vb)]  
  
## 관련 규칙  
 [CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: ISerializable을 올바르게 구현하십시오.](../Topic/CA2240:%20Implement%20ISerializable%20correctly.md)  
  
 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: serialization 메서드를 올바르게 구현하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
  
 [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
 [CA2120: serialization 생성자를 안전하게 하십시오.](../Topic/CA2120:%20Secure%20serialization%20constructors.md)