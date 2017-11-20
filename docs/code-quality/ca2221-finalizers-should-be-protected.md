---
title: "CA2221: 종료자는 protected 여야 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2221
- FinalizersShouldBeProtected
helpviewer_keywords:
- FinalizersShouldBeProtected
- CA2221
ms.assetid: bda03aee-4cce-45d3-907d-17f4ee030acc
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8ff2d5cd64a77f09437a07b446f486e1c2dd5024
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2221-finalizers-should-be-protected"></a>CA2221: 종료자는 protected여야 합니다.
|||  
|-|-|  
|TypeName|FinalizersShouldBeProtected|  
|CheckId|CA2221|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 공용 형식 패밀리 (protected) 액세스를 지정 하지 않는 종료자를 구현 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 종료자에서는 패밀리 액세스 한정자를 사용해야 합니다. 이 규칙은 C#, Visual Basic 및 Visual c + + 컴파일러에서 적용 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 제품군 액세스할 수 있도록 종료자를 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 높은 수준의 모든.NET 언어;에이 규칙 위반 되지 않습니다. Microsoft Intermediate Language를 작성 하는 경우 위반 될 수 있습니다.  
  
```  
// =============== CLASS MEMBERS DECLARATION ===================  
//   note that class flags, 'extends' and 'implements' clauses  
//          are provided here for information only  
  
.namespace UsageLibrary  
{  
  .class public auto ansi beforefieldinit FinalizeMethodNotProtected  
         extends [mscorlib]System.Object  
  {  
    .method public hidebysig instance void  
            Finalize() cil managed  
    {  
  
      // Code size       1 (0x1)  
      .maxstack  0  
      IL_0000:  ret  
    } // end of method FinalizeMethodNotProtected::Finalize  
  
    .method public hidebysig specialname rtspecialname  
            instance void  .ctor() cil managed  
    {  
      // Code size       7 (0x7)  
      .maxstack  1  
      IL_0000:  ldarg.0  
      IL_0001:  call       instance void [mscorlib]System.Object::.ctor()  
      IL_0006:  ret  
    } // end of method FinalizeMethodNotProtected::.ctor  
  
  } // end of class FinalizeMethodNotProtected  
} // end of namespace  
```  
  
## <a name="see-also"></a>참고 항목  
 [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)