---
title: "CA1017: ComVisibleAttribute로 어셈블리 표시 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5e4c76efff009c85f9d607611d92d53cad5d2759
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017: ComVisibleAttribute로 어셈블리 표시
|||  
|-|-|  
|TypeName|MarkAssembliesWithComVisible|  
|CheckId|CA1017|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 어셈블리에 없는 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 특성이 적용 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 특성 COM 클라이언트가 관리 되는 코드를 액세스 하는 방법을 결정 합니다. 어셈블리에서 COM에 노출할지 여부를 명시적으로 나타내는 것이 좋은 디자인입니다. COM 노출 여부 전체 어셈블리에 대 한 설정 하 고 개별 형식 및 형식 멤버를 재정의할 수 있습니다. 특성이 없는 경우 어셈블리의 내용이 COM 클라이언트에 표시 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 어셈블리에 특성을 추가 합니다. 어셈블리를 COM 클라이언트에 노출 하지 않으려면 특성을 적용 하 고 해당 값을 설정 `false`합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다. 어셈블리를 노출 하려는 경우 특성을 적용 하 고 해당 값을 설정 `true`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 어셈블리를는 <xref:System.Runtime.InteropServices.ComVisibleAttribute> COM 클라이언트에 게 표시 되지 않도록 적용 된 특성입니다.  
  
 [!code-cpp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CPP/ca1017-mark-assemblies-with-comvisibleattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/VisualBasic/ca1017-mark-assemblies-with-comvisibleattribute_1.vb)]
 [!code-csharp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CSharp/ca1017-mark-assemblies-with-comvisibleattribute_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)   
 [상호 운용할 .NET 형식의 정규화](/dotnet/framework/interop/qualifying-net-types-for-interoperation)