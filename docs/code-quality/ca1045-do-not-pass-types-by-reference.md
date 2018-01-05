---
title: "CA1045: 참조로 형식을 전달 하지 마십시오 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1045
- DoNotPassTypesByReference
helpviewer_keywords:
- CA1045
- DoNotPassTypesByReference
ms.assetid: bcc3900a-e092-4bb8-896f-cb83f6289968
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7542e21963f272dd10180203a52bee9994de2cdc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1045-do-not-pass-types-by-reference"></a>CA1045: 참조로 참조 형식을 전달하지 않습니다.
|||  
|-|-|  
|TypeName|DoNotPassTypesByReference|  
|CheckId|CA1045|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 공용 형식에서 public 또는 protected 메서드에 `ref` 매개 변수는 기본 형식, 참조 형식 또는 값 형식이 사용 하는 기본 제공 형식 중 하나가 아닙니다.  
  
## <a name="rule-description"></a>규칙 설명  
 참조로 형식을 전달 (사용 하 여 `out` 또는 `ref`) 포인터를 값 형식과 참조 형식, 어떻게 다른 지를 이해 하 고 여러 값을 반환 하는 메서드를 처리 해야 합니다. 또한 간의 차이 `out` 및 `ref` 매개 변수는 잘 알려져 있지 않습니다.  
  
 참조 형식이 "참조"에 의해 전달 되 면 메서드를 사용 하려고 하기 매개 변수 개체의 다른 인스턴스를 반환 합니다. (참조 형식을 참조로 전달는 또한 다음 이라고 알려집니다 double 포인터, 포인터 또는 이중 간접 참조에 대 한 포인터를 사용 합니다.) 호출 규칙, 즉 "" 값으로 전달 기본값을 사용 하 여 참조 형식을 이미 사용 하는 매개 변수 개체에 대 한 포인터를 받습니다. 포인터를 가리키는, 개체가 아닌 값으로 전달 됩니다. 포인터 참조의 새 인스턴스를 가리키도록 변경할 수 있다는 것을 의미 하지만 가리키는 개체의 내용을 변경할 수 값으로 전달 합니다. 대부분의 응용 프로그램에 대 한 충분 한 이므로 원하는 동작을 수행할 수 있습니다.  
  
 메서드가 해야 다른 인스턴스를 반환 하는이를 위해 메서드의 반환 값을 사용 합니다. 참조는 <xref:System.String?displayProperty=fullName> 다양 한 문자열에서 작동 하 고 문자열의 새 인스턴스를 반환 하는 방법에 대 한 클래스입니다. 이 모델을 사용 하 여 원래 개체의 유지 여부를 결정 하 고 호출자에 게 유지 됩니다.  
  
 반환 값은 일반적 이며의 올바른 응용 프로그램을 많이 사용 되지만 `out` 및 `ref` 중간 디자인과 코딩 기술을 매개 변수가 필요 합니다. 일반 사용자를 대상으로 작업에 능숙 할 사용자가 기대 하지에 대 한 디자인 하는 라이브러리 설계자 `out` 또는 `ref` 매개 변수입니다.  
  
> [!NOTE]
>  매개 변수를 큰 구조를 사용 하는 경우 값으로 전달 이러한 구조를 복사 하는 데 필요한 추가 리소스 성능 효과 발생할 수 있습니다. 이러한 경우를 고려해 볼 수 있습니다를 사용 하 여 `ref` 또는 `out` 매개 변수입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 값 형식 발생 하는이 규칙 위반 문제를 해결 하려면 메서드가 반환 값으로 개체를 반환 했습니다. 이 메서드는 여러 값을 반환 해야는 값을 포함 하는 개체의 단일 인스턴스를 반환 하도록 다시 디자인 합니다.  
  
 참조 형식 발생 하는이 규칙 위반 문제를 해결 하려면 원하는 동작 참조의 새 인스턴스를 반환 하려면 인지를 확인 합니다. 이면 메서드는 이렇게 하려면 반환 값을 사용 해야 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙;에서 경고를 표시 하지 않아도 안전 합니다. 그러나이 디자인 유용성 문제가 발생할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 라이브러리에는 사용자의 피드백에 대 한 응답을 생성 하는 클래스의 두 가지 구현을 보여 줍니다. 첫 번째 구현 (`BadRefAndOut`)을 설정 하면 라이브러리 사용자 3 개의 반환 값을 관리할 수 있습니다. 두 번째 구현 (`RedesignedRefAndOut`) 컨테이너 클래스의 인스턴스를 반환 하 여 사용자 환경을 단순화 (`ReplyData`) 하나의 단위로 데이터를 관리 하는입니다.  
  
 [!code-csharp[FxCop.Design.NoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_1.cs)]  
  
## <a name="example"></a>예  
 다음 응용 프로그램 사용자의 경험을 보여 줍니다. 다시 디자인 된 라이브러리에 대 한 호출 (`UseTheSimplifiedClass` 메서드)는 더 간단 및 메서드에 의해 반환 되는 정보를 손쉽게 관리할 수 있습니다. 두 방법 중에서 출력은 동일 합니다.  
  
 [!code-csharp[FxCop.Design.TestNoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_2.cs)]  
  
## <a name="example"></a>예  
 다음 예제 라이브러리에서는 어떻게 `ref` 참조 형식에 대 한 매개 변수 사용 되 고이 기능을 구현 하는 더 나은 방법을 보여줍니다.  
  
 [!code-csharp[FxCop.Design.RefByRefNo#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_3.cs)]  
  
## <a name="example"></a>예  
 다음 응용 프로그램 동작을 보여 주기 위해 라이브러리에서 각 메서드를 호출 합니다.  
  
 [!code-csharp[FxCop.Design.TestRefByRefNo#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_4.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
 **값으로 전달 하는 포인터-변경:**  
**12345**  
**12345**  
**포인터-참조로 전달 변경:**  
**12345**  
**12345 ABCDE**  
**반환 값으로 전달 합니다.**  
**12345 ABCDE**   
## <a name="related-rules"></a>관련된 규칙  
 [CA1021: out 매개 변수를 사용하지 마십시오.](../code-quality/ca1021-avoid-out-parameters.md)