---
title: "CA1017: ComVisibleAttribute로 어셈블리 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1017"
  - "MarkAssembliesWithComVisible"
helpviewer_keywords: 
  - "MarkAssembliesWithComVisible"
  - "CA1017"
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1017: ComVisibleAttribute로 어셈블리 표시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MarkAssembliesWithComVisible|  
|CheckId|CA1017|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 어셈블리에 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 특성이 적용되어 있지 않습니다.  
  
## 규칙 설명  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 특성에 따라 COM 클라이언트가 관리 코드에 액세스하는 방식이 달라집니다.  어셈블리에서 COM에 노출할지 여부를 명시적으로 나타내는 것이 좋은 디자인입니다.  전체 어셈블리에 대해 COM 표시 유형을 설정한 다음 개별 형식 및 형식 멤버에 대해 이를 재정의할 수 있습니다.  이 특성이 없으면 COM 클라이언트에서 어셈블리의 내용을 볼 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 어셈블리에 해당 특성을 추가합니다.  COM 클라이언트에서 어셈블리를 볼 수 없도록 하려면 특성을 적용한 다음 그 값을 `false`로 설정합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  어셈블리를 노출하려면 특성을 적용한 다음 그 값을 `true`로 설정합니다.  
  
## 예제  
 다음 예제에서는 COM 클라이언트에서 볼 수 없도록 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 특성이 적용된 어셈블리를 보여 줍니다.  
  
 [!code-cpp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CPP/ca1017-mark-assemblies-with-comvisibleattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/VisualBasic/ca1017-mark-assemblies-with-comvisibleattribute_1.vb)]
 [!code-cs[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CSharp/ca1017-mark-assemblies-with-comvisibleattribute_1.cs)]  
  
## 참고 항목  
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [상호 운용할 .NET 형식의 정규화](../Topic/Qualifying%20.NET%20Types%20for%20Interoperation.md)