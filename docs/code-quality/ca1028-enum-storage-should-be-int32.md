---
title: "CA1028: 열거형 저장소는 Int32여야 합니다. | Microsoft Docs"
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
  - "CA1028"
  - "EnumStorageShouldBeInt32"
helpviewer_keywords: 
  - "CA1028"
  - "EnumStorageShouldBeInt32"
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1028: 열거형 저장소는 Int32여야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|EnumStorageShouldBeInt32|  
|CheckId|CA1028|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 열거형의 내부 형식이 <xref:System.Int32?displayProperty=fullName>가 아닙니다.  
  
## 규칙 설명  
 열거형은 서로 관련 있는 명명된 상수 집합을 정의하는 값 형식입니다.  기본적으로 <xref:System.Int32?displayProperty=fullName> 데이터 형식은 상수 값을 저장하는 데 사용됩니다.  이 내부 형식을 변경할 수 있지만 대부분의 시나리오에서 변경할 필요가 없으며 변경하지 않는 것이 좋습니다.  <xref:System.Int32>보다 작은 데이터 형식을 사용해도 성능이 크게 향상되는 것은 아닙니다.  기본 데이터 형식을 사용할 수 없으면 CLS\(Common Language System\) 규격의 정수 계열 형식인 <xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32> 또는 <xref:System.Int64> 중 하나를 사용하여 모든 열거형 값을 CLS 규격 프로그래밍 언어로 나타낼 수 있도록 해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 크기나 호환성 문제가 없는 경우 <xref:System.Int32>를 사용합니다.  <xref:System.Int32>의 크기가 값을 저장하기에 충분하지 않으면 <xref:System.Int64>를 사용합니다.  이전 버전과의 호환성 때문에 더 작은 데이터 형식이 필요할 경우에는 <xref:System.Byte> 또는 <xref:System.Int16>을 사용하십시오.  
  
## 경고를 표시하지 않는 경우  
 이전 버전과의 호환성 문제를 해결하기 위해 필요한 경우에만 이 규칙에서 경고를 표시하지 않도록 설정하십시오.  응용 프로그램에서는 이 규칙을 따르지 않더라도 대개 문제가 발생하지 않습니다.  언어 상호 운용성이 필요한 라이브러리에서는 이 규칙을 따르지 않는 경우 사용자에게 부정적인 영향을 줄 수 있습니다.  
  
## 규칙 위반 예  
  
### 설명  
 다음 예제에서는 권장되는 내부 데이터 형식을 사용하지 않는 두 가지 열거형을 보여 줍니다.  
  
### 코드  
 [!code-vb[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_1.vb)]
 [!code-cs[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_1.cs)]  
  
## 수정 방법 예  
  
### 설명  
 다음 예제에서는 내부 데이터 형식을 <xref:System.Int32>로 변경하여 앞의 규칙 위반 문제를 해결합니다.  
  
### 코드  
 [!code-cs[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_2.cs)]
 [!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_2.vb)]  
  
## 관련 규칙  
 [CA1008: 열거형에는 0 값이 있어야 합니다.](../code-quality/ca1008-enums-should-have-zero-value.md)  
  
 [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
 [CA1700: 열거형 값의 이름을 'Reserved'로 지정하지 마십시오.](../code-quality/ca1700-do-not-name-enum-values-reserved.md)  
  
 [CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마십시오.](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)  
  
## 참고 항목  
 <xref:System.Byte?displayProperty=fullName>   
 <xref:System.Int16?displayProperty=fullName>   
 <xref:System.Int32?displayProperty=fullName>   
 <xref:System.Int64?displayProperty=fullName>