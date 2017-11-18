---
title: "CA2114: 메서드 보안은 이어야 형식의 상위 집합 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d9784ae650a411ef4fe5086ae8bf756147fd2365
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: 메서드 보안은 형식의 상위 집합이어야 합니다.
|||  
|-|-|  
|TypeName|MethodSecurityShouldBeASupersetOfType|  
|CheckId|CA2114|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 형식에 선언적 보안 및 해당 메서드 중 하나에 동일한 보안 작업에 대 한 선언적 보안 및 보안 작업은 없습니다 [링크 요청](/dotnet/framework/misc/link-demands) 또는 [상속 요청](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9), 한 권한과 메서드에서 검사 권한의 하위 집합이 아닌 형식에서 검사 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 메서드가 동일한 작업에 대해 메서드 수준과 형식 수준의 선언적 보안이 모두 없어야 합니다. 두 가지 검사 결합 되지 않습니다. 메서드 수준 요청에만 적용 됩니다. 예를 들어, 권한을 요구 하는 형식 `X`, 권한을 요구 하는 메서드 중 하나 및 `Y`, 코드 권한이 없는 `X` 메서드를 실행 하 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 두 가지 동작 모두 필요한 지 확인 하기 위해 코드를 검토 합니다. 두 작업이 필요한 경우에 메서드 수준의 작업 형식 수준에서 지정 된 보안 포함 되어 있는지 확인 합니다. 예를 들어, 권한을 요구 하는 형식이 `X`, 권한을 요청 해야 하 고 `Y`, 메서드가 명시적으로 요청 해야 `X` 및 `Y`합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 메서드는 형식으로 지정 하는 보안 필요 하지 않은 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 그러나이 일반적인 시나리오가 아니며 신중 하 게 디자인 검토에 대 한 요구가 나타낼 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는이 규칙을 위반의 위험성을 보여 주기 위해 환경 권한을 사용 합니다. 이 예제에서는 응용 프로그램 코드 형식에 필요한 사용 권한을 거부 하기 전에 보안 된 형식의 인스턴스를 만듭니다. 실제 위협 시나리오에서는 응용 프로그램에는 개체의 인스턴스를 가져오는 다른 방법이 필요 합니다.  
  
 다음 예제에서 라이브러리 요구는 형식에 대 한 권한을 쓰고 메서드에 대 한 읽기 권한이 있습니다.  
  
 [!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]  
  
## <a name="example"></a>예제  
 다음 응용 프로그램 코드 형식 수준 보안 요구 사항을 충족 하지 않는 경우에 메서드를 호출 하 여 라이브러리의 취약성을 보여 줍니다.  
  
 [!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
 **[모든 사용 권한을] 개인 정보: 6/16/1964 오전 12시: 00**  
**[쓰기 권한이 없는 경우 (유형별 요구)] 개인 정보: 6/16/1964 오전 12시: 00**  
**[읽기 권한 (메서드에 의해 요구) 없음] 개인 정보에 액세스할 수 없습니다: 요청에 실패 했습니다.**   
## <a name="see-also"></a>참고 항목  
 [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)   
 [상속 요청](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9)   
 [링크 요구](/dotnet/framework/misc/link-demands)   
 [데이터 및 모델링](/dotnet/framework/data/index)