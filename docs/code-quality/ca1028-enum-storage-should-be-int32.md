---
title: "CA1028: 열거형 저장소는 i n t 32 여야 합니다 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1028
- EnumStorageShouldBeInt32
helpviewer_keywords:
- EnumStorageShouldBeInt32
- CA1028
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b09082cd78b3b78dda28201e85099e87f87d8ad4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028: 열거형 저장소는 Int32여야 합니다.
|||  
|-|-|  
|TypeName|EnumStorageShouldBeInt32|  
|CheckId|CA1028|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 Public 열거형의 내부 형식에는 없는 <xref:System.Int32?displayProperty=fullName>합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 열거형은 서로 관련 있는 명명된 상수 집합을 정의하는 값 형식입니다. 기본적으로는 <xref:System.Int32?displayProperty=fullName> 데이터 형식은 상수 값을 저장 하는 데 사용 됩니다. 내부 형식은 변경할 수 있습니다, 경우에 아닙니다 필요 하거나 권장 대부분의 시나리오에 대 한. 성능이 크게 향상 되지 않습니다는 보다 작은 데이터 형식을 사용 하 여 수행할 <xref:System.Int32>합니다. 공용 언어 시스템 (CLS) 중 하나를 사용 해야 기본 데이터 형식을 사용할 수 없는 경우-규격 정수 계열 형식을 <xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32>, 또는 <xref:System.Int64> 열거형의 모든 값에 표시할 수 있는지 확인 하려면 CLS 규격 프로그래밍 언어입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 크기나 호환성 문제가 존재 하지 않는 한이 규칙 위반의 문제를 해결 하려면 사용 <xref:System.Int32>합니다. 상황에 대 한 여기서 <xref:System.Int32> 이 너무 작아 값을 포함을 사용 하 여 <xref:System.Int64>합니다. 더 작은 데이터 형식이 필요로 하는 이전 버전과 호환성을 사용 하 여 <xref:System.Byte> 또는 <xref:System.Int16>합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이전 버전과 호환성 문제에 필요한 경우에이 규칙에서 경고를 표시 합니다. 응용 프로그램에서 일반적으로이 규칙을 따르지 않으면에 문제가 발생 하지 않습니다. 언어 상호 운용성이 필요한 라이브러리에이 규칙을 따르지 않으면 사용자가 저하 될 수 있습니다.  
  
## <a name="example-of-a-violation"></a>위반의 예로  
  
### <a name="description"></a>설명  
 다음 예에서는 권장 되는 기본 데이터 형식을 사용 하지 않는 열거형이 두 개를 보여 줍니다.  
  
### <a name="code"></a>코드  
 [!code-vb[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_1.vb)]
 [!code-csharp[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_1.cs)]  
  
## <a name="example-of-how-to-fix"></a>수정 하는 방법의 예  
  
### <a name="description"></a>설명  
 다음 예제에서는 기본 데이터 형식을 변경 하 여 위반을 해결 <xref:System.Int32>합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_2.cs)]
 [!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_2.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1008: 열거형에는 0 값이 있어야 합니다.](../code-quality/ca1008-enums-should-have-zero-value.md)  
  
 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
 [CA1700: 열거형 값의 이름을 'Reserved'로 지정하지 마십시오.](../code-quality/ca1700-do-not-name-enum-values-reserved.md)  
  
 [CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마십시오.](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Byte?displayProperty=fullName>   
 <xref:System.Int16?displayProperty=fullName>   
 <xref:System.Int32?displayProperty=fullName>   
 <xref:System.Int64?displayProperty=fullName>