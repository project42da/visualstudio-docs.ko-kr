---
title: "CA2221: 종료자는 protected여야 합니다. | Microsoft Docs"
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
  - "CA2221"
  - "FinalizersShouldBeProtected"
helpviewer_keywords: 
  - "CA2221"
  - "FinalizersShouldBeProtected"
ms.assetid: bda03aee-4cce-45d3-907d-17f4ee030acc
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2221: 종료자는 protected여야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|FinalizersShouldBeProtected|  
|CheckId|CA2221|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 public 형식이 패밀리\(protected\) 액세스를 지정하지 않는 종료자를 구현합니다.  
  
## 규칙 설명  
 종료자에서는 패밀리 액세스 한정자를 사용해야 합니다.  이 규칙은 C\#, Visual Basic 및 Visual C\+\+ 컴파일러를 통해 적용됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 패밀리 액세스가 가능하도록 종료자를 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 높은 수준의 .NET 언어에서는 이 규칙이 위반되지 않습니다. MSIL\(Microsoft Intermediate Language\)을 작성할 경우에는 이 규칙이 위반될 수 있습니다.  
  
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
  
## 참고 항목  
 [삭제 패턴](../Topic/Dispose%20Pattern.md)