---
title: "CA1303: 리터럴을 지역화된 매개 변수로 전달하지 마십시오. | Microsoft Docs"
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
  - "Do not pass literals as localized parameters"
  - "DoNotPassLiteralsAsLocalizedParameters"
  - "CA1303"
helpviewer_keywords: 
  - "CA1303"
  - "DoNotPassLiteralsAsLocalizedParameters"
ms.assetid: 904d284e-76d0-4b8f-a4df-0094de8d7aac
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1303: 리터럴을 지역화된 매개 변수로 전달하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotPassLiteralsAsLocalizedParameters|  
|CheckId|CA1303|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드가 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리의 생성자 또는 메서드에 문자열 리터럴을 매개 변수로 전달하는데 이 문자열은 지역화될 수 있어야 합니다.  
  
 이 경고는 리터럴 문자열이 매개 변수 또는 속성에 대한 값으로 전달되고 다음 사례 중 하나 이상이 참일 때 발생합니다.  
  
-   매개 변수 또는 속성의 <xref:System.ComponentModel.LocalizableAttribute> 특성은 true로 설정됩니다.  
  
-   매개 변수 또는 속성 이름에 "Text", "Message" 또는 "Caption"이 포함되어 있습니다.  
  
-   Console.Write or Console.WriteLine 메서드에 전달되는 문자열 매개 변수의 이름은 "값" 또는 "형식"입니다.  
  
## 규칙 설명  
 소스 코드에 포함된 문자열 리터럴은 지역화하기 어렵습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 문자열 리터럴을 <xref:System.Resources.ResourceManager> 클래스의 인스턴스를 통해 검색한 문자열로 바꿉니다.  
  
## 경고를 표시하지 않는 경우  
 코드 라이브러리가 지역화되지 않는 경우 또는 코드 라이브러리를 사용하는 개발자 또는 최종 사용자에게 문자열이 노출되지 않는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
 사용자는 명명된 매개 변수 또는 속성의 이름을 바꾸거나 이러한 항목을 조건부로 만들어서 지역화된 문자열을 전달하면 안 되는 메서드에 방해가 되는 요소를 제거할 수 있습니다.  
  
## 예제  
 다음 예제에서는 두 인수 중 하나가 범위를 벗어나면 예외를 throw하는 메서드를 보여 줍니다.  첫 번째 인수의 경우 예외 생성자에 이 규칙을 위반하는 리터럴 문자열이 전달됩니다.  두 번째 인수의 경우 생성자에 <xref:System.Resources.ResourceManager>를 통해 검색된 문자열이 제대로 전달됩니다.  
  
 [!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CPP/ca1303-do-not-pass-literals-as-localized-parameters_1.cpp)]
 [!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/VisualBasic/ca1303-do-not-pass-literals-as-localized-parameters_1.vb)]
 [!code-cs[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CSharp/ca1303-do-not-pass-literals-as-localized-parameters_1.cs)]  
  
## 참고 항목  
 [데스크톱 응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)