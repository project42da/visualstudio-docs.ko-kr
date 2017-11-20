---
title: "CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
helpviewer_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a5379defde7ace66f43cad0983c9b14b554fb232
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2236-call-base-class-methods-on-iserializable-types"></a>CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.
|||  
|-|-|  
|TypeName|CallBaseClassMethodsOnISerializableTypes|  
|CheckId|CA2236|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 구현 하는 형식에서 파생 되는 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스와 다음 조건 중 하나가 참인:  
  
-   형식은 serialization 생성자를 사용 하는 생성자, 구현에서 <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>, <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> 매개 변수 시그니처에 하지만 기본 형식의 serialization 생성자를 호출 하지는 않습니다.  
  
-   형식에서 구현 하는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 메서드 하지만 호출 하지 않습니다는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 기본 형식의 메서드.  
  
## <a name="rule-description"></a>규칙 설명  
 사용자 지정 serialization 프로세스에는 형식이 구현 하는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 해당 필드와 필드를 역직렬화 할 serialization 생성자를 serialize 하는 메서드. 형식을 구현 하는 형식에서 파생 되는 경우는 <xref:System.Runtime.Serialization.ISerializable> 인터페이스, 기본 형식 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드 및 serialization 생성자를 호출 해야 serialize/de-serialize 하는 기본 형식의 필드입니다. 그렇지 않으면 형식은 되지 직렬화 되며 올바르게 deserialize 합니다. 파생된 된 형식의 새 필드를 추가 하지 않으면, 유형이 필요는 없습니다 구현 하는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드나 serialization 생성자 하거나 해당 하는 기본 형식 요소를 호출 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 기본 형식 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드나 serialization 생성자는 해당 파생 된 형식의 메서드나 생성자입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 serialization 생성자를 호출 하 여 규칙을 충족 하는 파생 된 형식 및 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 기본 클래스의 메서드.  
  
 [!code-vb[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/VisualBasic/ca2236-call-base-class-methods-on-iserializable-types_1.vb)]
 [!code-csharp[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/CSharp/ca2236-call-base-class-methods-on-iserializable-types_1.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2240: ISerializable을 올바르게 구현하십시오.](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: serialization 메서드를 올바르게 구현하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
  
 [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
 [CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: serialization 생성자를 안전하게 하십시오.](../code-quality/ca2120-secure-serialization-constructors.md)