---
title: "CA2105: 배열 필드는 읽기 전용이면 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2105"
  - "ArrayFieldsShouldNotBeReadOnly"
helpviewer_keywords: 
  - "ArrayFieldsShouldNotBeReadOnly"
  - "CA2105"
ms.assetid: 0bdc3421-3ceb-4182-b30c-a992fbfcc35d
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2105: 배열 필드는 읽기 전용이면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ArrayFieldsShouldNotBeReadOnly|  
|CheckId|CA2105|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 배열을 보유하는 public 또는 protected 필드가 읽기 전용으로 선언되었습니다.  
  
## 규칙 설명  
 배열이 들어 있는 필드에 `readonly`\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `ReadOnly`\) 한정자를 적용하면 필드를 변경하여 다른 배열을 참조할 수 없습니다.  그러나 읽기 전용 필드에 저장된 배열의 요소는 변경할 수 있습니다.  공개적으로 액세스할 수 있는 읽기 전용 배열의 요소를 기반으로 결정을 내리거나 작업을 수행하는 코드에는 보안상 취약한 부분이 있을 수 있습니다.  
  
 공용 필드를 사용하면 디자인 규칙 [CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오.](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)도 위반하게 됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙에 의해 식별된 보안 취약점을 해결하려면 공개적으로 액세스할 수 있는 읽기 전용 배열의 내용은 사용하지 않도록 합니다.  다음 절차 중 하나를 사용하는 것이 좋습니다.  
  
-   배열을 변경할 수 없는 강력한 형식의 컬렉션으로 바꿉니다.  자세한 내용은 <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>을 참조하십시오.  
  
-   공용 필드를 private 배열의 복제본을 반환하는 메서드로 바꿉니다.  이렇게 하면 코드에서 복제본을 사용하지 않기 때문에 요소가 수정되더라도 위험하지 않습니다.  
  
 두 번째 방법을 선택한 경우 필드를 속성으로 바꾸지 마십시오. 배열을 반환하는 속성을 사용하면 성능이 저하됩니다.  자세한 내용은 [CA1819: 속성은 배열을 반환해서는 안 됩니다.](../code-quality/ca1819-properties-should-not-return-arrays.md)을 참조하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서 경고를 제외하지 않는 것이 좋습니다.  읽기 전용 필드의 내용이 중요하지 않은 경우는 거의 발생하지 않습니다.  그러나 중요하지 않은 경우라면 메시지를 제외하는 대신 `readonly` 한정자를 제거하십시오.  
  
## 예제  
 이 예제에서는 이 규칙을 위반했을 경우의 위험을 보여 줍니다.  첫 번째 부분에서는 `MyClassWithReadOnlyArrayField` 형식이 있는 예제 라이브러리를 보여 줍니다. 이 형식에는 보안되지 않는 `grades` 및 `privateGrades`라는 두 필드가 포함되어 있습니다.  `grades` 필드는 public이기 때문에 모든 호출자에게 노출되어 취약합니다.  `privateGrades` 필드는 private이지만 `GetPrivateGrades` 메서드가 이를 호출자에게 반환하므로 여전히 취약합니다.  `securePrivateGrades` 필드는 `GetSecurePrivateGrades` 메서드를 통해 안전한 방식으로 노출됩니다.  이 필드는 권장 디자인 방식에 따라 private으로 선언됩니다.  두 번째 부분에서는 `grades` 및 `privateGrades` 멤버에 저장된 값을 변경하는 코드를 보여 줍니다.  
  
 다음은 예제 클래스 라이브러리입니다.  
  
 [!code-cs[FxCop.Security.ArrayFieldsNotReadOnly#1](../code-quality/codesnippet/CSharp/ca2105-array-fields-should-not-be-read-only_1.cs)]  
  
## 예제  
 다음 코드에서는 예제 클래스 라이브러리를 사용하여 읽기 전용 배열 보안 문제를 보여 줍니다.  
  
 [!code-cs[FxCop.Security.TestArrayFieldsRead#1](../code-quality/codesnippet/CSharp/ca2105-array-fields-should-not-be-read-only_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **무단 변경 전: 등급: 90, 90, 90 개인 등급: 90, 90, 90  보안 등급, 90, 90, 90**  
**무단 변경 후: 등급: 90, 555, 90 개인 등급: 90, 555, 90  보안 등급, 90, 90, 90**   
## 참고 항목  
 <xref:System.Array?displayProperty=fullName>   
 <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>