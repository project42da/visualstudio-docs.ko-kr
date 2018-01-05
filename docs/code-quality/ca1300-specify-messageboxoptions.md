---
title: "CA1300: MessageBoxOptions를 지정 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b47c5f2297d9b13e33dc064a203bfd84ce2d196f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300: MessageBoxOptions를 지정하십시오.
|||  
|-|-|  
|TypeName|SpecifyMessageBoxOptions|  
|CheckId|CA1300|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 메서드 호출의 오버 로드는 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> 사용 하지 않는 메서드는 <xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName> 인수입니다.  
  
## <a name="rule-description"></a>규칙 설명  
 오른쪽에서 왼쪽 읽기 순서를 사용 하는 문화권에 맞게 메시지 상자를 표시 하는 <xref:System.Windows.Forms.MessageBoxOptions> 및 <xref:System.Windows.Forms.MessageBoxOptions> 의 멤버는 <xref:System.Windows.Forms.MessageBoxOptions> 열거형에 전달 되어야 합니다는 <xref:System.Windows.Forms.MessageBox.Show%2A> 메서드. 검사는 <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName> 오른쪽에서 왼쪽 읽기 순서를 사용할지 결정을 포함 하는 컨트롤의 속성입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 호출의 오버 로드는 <xref:System.Windows.Forms.MessageBox.Show%2A> 를 받는 메서드에 <xref:System.Windows.Forms.MessageBoxOptions> 인수입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 코드 라이브러리가 오른쪽에서 왼쪽 읽기 순서를 사용 하는 문화권에 대 한 지역화 되지 않을 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 문화권의 읽기 순서에 대 한 적합 한 옵션이 있는 메시지 상자를 표시 하는 메서드를 보여 줍니다. 표시 되지 않는 리소스 파일을 예제를 빌드하려면 필요 합니다. 리소스 파일 없이 예제를 빌드하려면 및 오른쪽에서 왼쪽으로 기능을 테스트 하려면 예제에 있는 설명은 코드를 따릅니다.  
  
 [!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
 [!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Resources.ResourceManager?displayProperty=fullName>   
 [데스크톱 앱의 리소스](/dotnet/framework/resources/index)