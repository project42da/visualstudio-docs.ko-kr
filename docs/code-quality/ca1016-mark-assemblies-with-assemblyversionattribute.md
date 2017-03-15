---
title: "CA1016: AssemblyVersionAttribute로 어셈블리 표시 | Microsoft Docs"
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
  - "MarkAssembliesWithAssemblyVersion"
  - "CA1016"
helpviewer_keywords: 
  - "CA1016"
  - "MarkAssembliesWithAssemblyVersion"
ms.assetid: 4340aed8-d92b-4cde-a398-cb6963c6da5a
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1016: AssemblyVersionAttribute로 어셈블리 표시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MarkAssembliesWithAssemblyVersion|  
|CheckId|CA1016|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 어셈블리에 버전 번호가 없습니다.  
  
## 규칙 설명  
 어셈블리의 ID는 다음 정보로 구성됩니다.  
  
-   어셈블리 이름  
  
-   버전 번호  
  
-   문화권  
  
-   공개 키\(강력한 이름의 어셈블리인 경우\)  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에서는 버전 번호를 사용하여 어셈블리를 고유하게 식별하고 강력한 이름이 지정된 어셈블리의 형식에 바인딩합니다.  버전 번호는 버전 및 게시자 정책과 함께 사용됩니다.  기본적으로 응용 프로그램은 해당 응용 프로그램이 빌드될 때 사용된 어셈블리 버전으로만 실행됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Reflection.AssemblyVersionAttribute?displayProperty=fullName> 특성을 사용하여 어셈블리에 버전 번호를 추가합니다.  다음 예제를 참조하십시오.  
  
## 경고를 표시하지 않는 경우  
 타사 또는 프로덕션 환경에서 사용되는 어셈블리에 대해서는 이 규칙에서 경고를 표시하십시오.  
  
## 예제  
 다음 예제에서는 <xref:System.Reflection.AssemblyVersionAttribute> 특성이 적용된 어셈블리를 보여 줍니다.  
  
 [!code-cs[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CSharp/ca1016-mark-assemblies-with-assemblyversionattribute_1.cs)]
 [!code-vb[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/VisualBasic/ca1016-mark-assemblies-with-assemblyversionattribute_1.vb)]
 [!code-cpp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CPP/ca1016-mark-assemblies-with-assemblyversionattribute_1.cpp)]  
  
## 참고 항목  
 [어셈블리 버전 관리](../Topic/Assembly%20Versioning.md)   
 [방법: 게시자 정책 만들기](../Topic/How%20to:%20Create%20a%20Publisher%20Policy.md)