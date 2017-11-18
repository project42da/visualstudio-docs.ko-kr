---
title: "CA2240: 구현 ISerializable 올바르게 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2240
- ImplementISerializableCorrectly
helpviewer_keywords:
- CA2240
- ImplementISerializableCorrectly
ms.assetid: cf05936d-0d6c-49ed-a1b4-220032e50b97
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c8e3f9ba0e3cb182ec08dd802dc87728a0fb9dc0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2240-implement-iserializable-correctly"></a>CA2240: ISerializable을 올바르게 구현하십시오.
|||  
|-|-|  
|TypeName|ImplementISerializableCorrectly|  
|CheckId|CA2240|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 에 할당할 수는 외부에서 볼 수 있는 형식이 고 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스와 다음 조건 중 하나가 참인:  
  
-   형식 상속 하지만 재정의 하지 않습니다는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> 메서드 및 형식 선언으로 표시 되지 않은 인스턴스 필드는 <xref:System.NonSerializedAttribute?displayProperty=fullName> 특성입니다.  
  
-   형식을 봉인 및 형식에서 구현 하는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 외부에서 표시 하 고 재정의 가능 하지 않은 방법을 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 인스턴스 상속 하는 형식에 선언 된 필드는 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> 인터페이스 serialization 프로세스에 자동으로 포함 되지 않습니다. 필드를 포함 하려면 유형을 구현 해야 합니다는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드와 serialization 생성자입니다. 필드를 직렬화 하지 않을 경우 적용 된 <xref:System.NonSerializedAttribute> 특성을 명시적으로 결정을 나타내기 위해 필드입니다.  
  
 구현 봉인 되지 않은 형식에는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 메서드 외부에 노출 해야 합니다. 따라서 메서드 파생된 형식에서 호출할 수 있으며 재정의할 수 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면는 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> 표시 되 고 재정의 가능한 메서드 모든 인스턴스 필드가 serialization 프로세스에 포함 하거나 명시적으로 표시 되었는지 확인 하 고는 <xref:System.NonSerializedAttribute> 특성입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 규칙을 위반 하는 두 직렬화 가능 유형을 보여 줍니다.  
  
 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_1.cs)]
 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_1.cpp)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는의 재정의 가능한 구현을 제공 하 여 두 개의 이전 위반을 해결 <xref:System.Runtime.Serialization.ISerializable.GetObjectData> Book 클래스에 및의 구현을 제공 하 여 `GetObjectData` 라이브러리 클래스에 있습니다.  
  
 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_2.cpp)]
 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_2.cs)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_2.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
 [CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)  
 [CA2238: serialization 메서드를 올바르게 구현하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
 [CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
 [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
 [CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
 [CA2120: serialization 생성자를 안전하게 하십시오.](../code-quality/ca2120-secure-serialization-constructors.md)  
