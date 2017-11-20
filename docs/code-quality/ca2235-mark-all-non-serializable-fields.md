---
title: "CA2235: 모든 순차 불가능 필드로 표시 하십시오. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2235
- MarkAllNonSerializableFields
helpviewer_keywords:
- CA2235
- MarkAllNonSerializableFields
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b6489cf400dd2f67c08ff4dba3bf6a1eda4ec46e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.
|||  
|-|-|  
|TypeName|MarkAllNonSerializableFields|  
|CheckId|CA2235|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 serialize할 수 없는 형식의 인스턴스 필드가 serialize할 수 있는 형식에 정의되었습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 직렬화 가능 형식이로 표시 된 하나는 <xref:System.SerializableAttribute?displayProperty=fullName> 특성입니다. 형식이 serialize 될 때는 <xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> 형식 직렬화 가능 하지 않은 형식의 인스턴스 필드를 포함 하는 경우 예외가 throw 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 적용 된 <xref:System.NonSerializedAttribute?displayProperty=fullName> 특성을 직렬화 할 수 없는 필드입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 경우에이 규칙에서 경고를 표시 하지는 <xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName> 직렬화 및 역직렬화 될 필드의 인스턴스를 허용 하는 형식이 선언 되었습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙을 위반 하는 형식 및 규칙을 충족 하는 형식을 보여 줍니다.  
  
 [!code-csharp[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/CSharp/ca2235-mark-all-non-serializable-fields_1.cs)]
 [!code-vb[FxCop.Usage.MarkNonSerializable#1](../code-quality/codesnippet/VisualBasic/ca2235-mark-all-non-serializable-fields_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: ISerializable을 올바르게 구현하십시오.](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: serialization 메서드를 올바르게 구현하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
 [CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: serialization 생성자를 안전하게 하십시오.](../code-quality/ca2120-secure-serialization-constructors.md)