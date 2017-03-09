---
title: "CA1300: MessageBoxOptions를 지정하십시오. | Microsoft Docs"
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
  - "SpecifyMessageBoxOptions"
  - "CA1300"
helpviewer_keywords: 
  - "SpecifyMessageBoxOptions"
  - "CA1300"
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1300: MessageBoxOptions를 지정하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|SpecifyMessageBoxOptions|  
|CheckId|CA1300|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드가 <xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName> 인수를 사용하지 않는 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> 메서드의 오버로드를 호출합니다.  
  
## 규칙 설명  
 오른쪽에서 왼쪽으로 읽기 순서를 사용하는 문화권에 대해 메시지 상자를 올바로 표시하려면 <xref:System.Windows.Forms.MessageBoxOptions> 열거형의 <xref:System.Windows.Forms.MessageBoxOptions> 및 <xref:System.Windows.Forms.MessageBoxOptions> 멤버를 <xref:System.Windows.Forms.MessageBox.Show%2A> 메서드로 전달해야 합니다.  오른쪽에서 왼쪽으로 읽기 순서를 사용할지 여부를 결정하려면 포함하는 컨트롤의 <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName> 속성을 검사하십시오.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Windows.Forms.MessageBoxOptions> 인수를 사용하는 <xref:System.Windows.Forms.MessageBox.Show%2A> 메서드의 오버로드를 호출합니다.  
  
## 경고를 표시하지 않는 경우  
 오른쪽에서 왼쪽으로 읽기 순서를 사용하는 문화권에 대해 코드 라이브러리가 지역화되지 않을 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 문화권의 읽기 순서에 적합한 옵션이 있는 메시지 상자를 표시하는 메서드를 보여 줍니다.  예제를 빌드하려면 리소스 파일이 필요합니다. 리소스 파일은 표시되지 않습니다.  예제에 있는 주석을 따라 리소스 파일 없이 예제를 빌드하고 오른쪽에서 왼쪽 기능을 테스트합니다.  
  
 [!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
 [!code-cs[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]  
  
## 참고 항목  
 <xref:System.Resources.ResourceManager?displayProperty=fullName>   
 [데스크톱 응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)