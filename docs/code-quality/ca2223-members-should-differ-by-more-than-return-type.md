---
title: ": 멤버 ca2223 반환 형식 이외의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MembersShouldDifferByMoreThanReturnType
- CA2223
helpviewer_keywords:
- CA2223
- MembersShouldDifferByMoreThanReturnType
ms.assetid: eb326d9f-50d9-48cb-84be-d41c84a8fe09
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 312ba498965cea7404e66d15f9136ac9a364da98
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2223-members-should-differ-by-more-than-return-type"></a>CA2223: 멤버는 반환 형식 이외의 것도 달라야 합니다.
|||  
|-|-|  
|TypeName|MembersShouldDifferByMoreThanReturnType|  
|CheckId|CA2223|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 두 public 또는 protected 멤버에 반환 형식을 제외 하면 동일한 서명이 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 공용 언어 런타임 면에서는 동일한 멤버를 구분할 수는 반환 형식 사용 하 고 허용 하지만이 기능은 공용 언어 사양에 없는 아닙니다.NET 프로그래밍 언어의 공통 기능이 아닙니다. 멤버는 반환 형식만 다를 때 개발자와 개발 도구가 수 제대로 구분 하지 해당 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면는 고유 이름, 매개 변수 형식이 기반 하거나 멤버를 노출 하지 않는 멤버의 디자인을 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제를 Microsoft intermediate language (MSIL)에서이 규칙을 위반 하는 형식을 보여줍니다. 공지는 C# 또는 Visual Basic.NET을 사용 하 여이 규칙을 위반 될 수 없습니다.  
  
```  
  
.namespace UsageLibrary  
{  
  .class public auto ansi beforefieldinit ReturnTypeTest  
         extends [mscorlib]System.Object  
  {  
    .method public hidebysig instance int32  
            AMethod(int32 x) cil managed  
    {  
      // Code size       6 (0x6)  
      .maxstack  1  
      .locals init (int32 V_0)  
      IL_0000:  ldc.i4.0  
      IL_0001:  stloc.0  
      IL_0002:  br.s       IL_0004  
  
      IL_0004:  ldloc.0  
      IL_0005:  ret  
    } // end of method ReturnTypeTest::AMethod  
  
    .method public hidebysig instance string  
            AMethod(int32 x) cil managed  
    {  
      // Code size       10 (0xa)  
      .maxstack  1  
      .locals init (string V_0)  
      IL_0000:  ldstr      "test"  
      IL_0005:  stloc.0  
      IL_0006:  br.s       IL_0008  
  
      IL_0008:  ldloc.0  
      IL_0009:  ret  
    } // end of method ReturnTypeTest::AMethod  
  
    .method public hidebysig specialname rtspecialname  
            instance void  .ctor() cil managed  
    {  
      // Code size       7 (0x7)  
      .maxstack  1  
      IL_0000:  ldarg.0  
      IL_0001:  call       instance void [mscorlib]System.Object::.ctor()  
      IL_0006:  ret  
    } // end of method ReturnTypeTest::.ctor  
  
  } // end of class ReturnTypeTest  
  
} // end of namespace UsageLibrary  
  
```