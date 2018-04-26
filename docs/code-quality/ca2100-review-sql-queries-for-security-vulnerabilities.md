---
title: 'CA2100: 보안상 취약한 부분이 있는지 SQL 쿼리를 검토하십시오.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- Review SQL queries for security vulnerabilities
- ReviewSqlQueriesForSecurityVulnerabilities
- CA2100
helpviewer_keywords:
- CA2100
- ReviewSqlQueriesForSecurityVulnerabilities
ms.assetid: 79670604-c02a-448d-9c0e-7ea0120bc5fe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: be39489c30de235248b9e3f2770811fc190ac5a3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2100-review-sql-queries-for-security-vulnerabilities"></a>CA2100: 보안상 취약한 부분이 있는지 SQL 쿼리를 검토하십시오.
|||
|-|-|
|TypeName|ReviewSqlQueriesForSecurityVulnerabilities|
|CheckId|CA2100|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 설정 하는 메서드는 <xref:System.Data.IDbCommand.CommandText%2A?displayProperty=fullName> 메서드에 문자열 인수 로부터 만들어진 문자열을 사용 하 여 속성입니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙에서는 문자열 인수에 사용자 입력이 포함된 것으로 가정합니다. 사용자 입력으로부터 만들어진 SQL 명령 문자열은 SQL 삽입 공격에 취약합니다. SQL 삽입 공격으로 악의적인 사용자는 손상 되거나 내부 데이터베이스에 무단으로 액세스 하기 위해에서 쿼리 디자인을 변경 하는 입력을 제공 합니다. 일반적인 기술 등의 단일 따옴표 또는 아포스트로피 SQL 리터럴 문자열 구분; 삽입 SQL 주석; 의미 하는 대시 두 개 및 세미콜론 새 명령을 따르는지를 나타냅니다. 사용자 입력에는 쿼리를 다음 중 하나를 사용의 일부 여야 하는 경우의 공격 위험을 줄이기 위해 효율성에 순서 대로 나열 합니다.

-   저장된 프로시저를 사용 합니다.

-   매개 변수가 있는 명령 문자열을 사용 합니다.

-   명령 문자열을 만들기 전에 형식과 내용에 대해 사용자 입력의 유효성을 검사 합니다.

 다음 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 형식은 구현 하는 <xref:System.Data.IDbCommand.CommandText%2A> 속성 또는 문자열 인수를 사용 하 여 속성을 설정 하는 생성자를 제공 합니다.

-   <xref:System.Data.Odbc.OdbcCommand?displayProperty=fullName> 및 <xref:System.Data.Odbc.OdbcDataAdapter?displayProperty=fullName>

-   <xref:System.Data.OleDb.OleDbCommand?displayProperty=fullName> 및 <xref:System.Data.OleDb.OleDbDataAdapter?displayProperty=fullName>

-   <xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName> 및 <xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>

-   <xref:System.Data.SqlClient.SqlCommand?displayProperty=fullName> 및 <xref:System.Data.SqlClient.SqlDataAdapter?displayProperty=fullName>

 명시적 또는 암시적으로 형식의 ToString 메서드를 사용할 때이 규칙이 위반 되 확인 쿼리 문자열을 생성 합니다. 다음은 예제입니다.

```
int x = 10;
string query = "SELECT TOP " + x.ToString() + " FROM Table";
```

 Tostring () 메서드를 재정의 하는 악의적인 사용자 수 때문에 규칙을 위반 합니다.

 또한 규칙 ToString 암시적으로 사용 하는 경우에 위반 됩니다.

```
int x = 10;
string query = String.Format("SELECT TOP {0} FROM Table", x);
```

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 매개 변수가 있는 쿼리를 사용 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 명령 텍스트에는 사용자 입력이 없는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

## <a name="example"></a>예제
 다음 예제에서는 메서드를 `UnsafeQuery`, 규칙을 위반 하는 메서드는 `SaferQuery`, 매개 변수가 있는 명령 문자열을 사용 하 여 규칙을 만족 하는 합니다.

 [!code-vb[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/VisualBasic/ca2100-review-sql-queries-for-security-vulnerabilities_1.vb)]
 [!code-csharp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CSharp/ca2100-review-sql-queries-for-security-vulnerabilities_1.cs)]
 [!code-cpp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CPP/ca2100-review-sql-queries-for-security-vulnerabilities_1.cpp)]

## <a name="see-also"></a>참고 항목
 [보안 개요](/dotnet/framework/data/adonet/security-overview)