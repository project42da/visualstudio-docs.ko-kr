---
title: "CA1016: AssemblyVersionAttribute로 어셈블리 표시 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MarkAssembliesWithAssemblyVersion
- CA1016
helpviewer_keywords:
- CA1016
- MarkAssembliesWithAssemblyVersion
ms.assetid: 4340aed8-d92b-4cde-a398-cb6963c6da5a
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 414a533e781be82cd0ffef1e9db234738ef07f16
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1016-mark-assemblies-with-assemblyversionattribute"></a>CA1016: AssemblyVersionAttribute로 어셈블리 표시
|||  
|-|-|  
|TypeName|MarkAssembliesWithAssemblyVersion|  
|CheckId|CA1016|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 어셈블리는 버전 번호가 없습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 어셈블리의 id는 다음 정보는 구성 됩니다.  
  
-   어셈블리 이름  
  
-   버전 번호  
  
-   문화권  
  
-   강력한 이름의 어셈블리 공개 키입니다.  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에서는 버전 번호를 사용하여 어셈블리를 고유하게 식별하고 강력한 이름이 지정된 어셈블리의 형식에 바인딩합니다. 버전 번호는 버전 및 게시자 정책과 함께 사용됩니다. 기본적으로 응용 프로그램은 해당 응용 프로그램이 빌드될 때 사용된 어셈블리 버전으로만 실행됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 버전 번호를 어셈블리에 사용 하 여 추가 된 <xref:System.Reflection.AssemblyVersionAttribute?displayProperty=fullName> 특성입니다. 다음 예제를 참조하십시오.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 제 3 자에서 또는 프로덕션 환경에서 사용 되는 어셈블리에 대 한이 규칙에서는 경고를에서 표시 하지 마십시오.  
  
## <a name="example"></a>예제  
 다음 예제에서는 어셈블리를는 <xref:System.Reflection.AssemblyVersionAttribute> 특성이 적용 합니다.  
  
 [!code-csharp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CSharp/ca1016-mark-assemblies-with-assemblyversionattribute_1.cs)]
 [!code-vb[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/VisualBasic/ca1016-mark-assemblies-with-assemblyversionattribute_1.vb)]
 [!code-cpp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CPP/ca1016-mark-assemblies-with-assemblyversionattribute_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [어셈블리 버전 관리](/dotnet/framework/app-domains/assembly-versioning)   
 [방법: 게시자 정책 만들기](/dotnet/framework/configure-apps/how-to-create-a-publisher-policy)