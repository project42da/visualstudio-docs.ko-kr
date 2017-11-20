---
title: "CA1409: Com 노출 형식 수 있어야 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
helpviewer_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c8d9fe357142cf8b95be0298797c4a18e9ee0df7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409: COM 노출 형식을 만들 수 있어야 합니다.
|||  
|-|-|  
|TypeName|ComVisibleTypesShouldBeCreatable|  
|CheckId|CA1409|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 특히 표시 유형 구성 요소 개체 모델 (COM)에 표시 된 참조 형식 매개 변수가 있는 public 생성자를 포함 하지만 공용 기본 (매개 변수가 없는) 생성자가 없습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 COM 클라이언트에서 공용 기본 생성자가 없는 형식을 만들 수 없습니다. 그러나 형식은 여전히 액세스할 수 있습니다 COM 클라이언트에서 다른 방법 형식을 만드는 예를 들어 (메서드 호출의 반환 값)을 통해 클라이언트에 전달 하는 데 사용할 수 있는 경우.  
  
 규칙에서 파생 된 형식을 무시 <xref:System.Delegate?displayProperty=fullName>합니다.  
  
 기본적으로 다음 COM에 표시 되지만: 어셈블리, public 형식, public 인스턴스 멤버를 공용 형식 및 공용 값 형식의 모든 멤버입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 공용 기본 생성자를 추가 또는 제거는 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 형식에서 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 만들고 개체를 COM 클라이언트에 전달 하는 다른 방법 제공 되는 경우이 규칙에서는 경고를에서 표시 하지 않는 안전 합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1017: 어셈블리를 ComVisibleAttribute로 표시하십시오.](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## <a name="see-also"></a>참고 항목  
 [상호 운용할 .NET 형식의 정규화](/dotnet/framework/interop/qualifying-net-types-for-interoperation)   
 [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)