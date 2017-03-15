---
title: "CA2100: 보안상 취약한 부분이 있는지 SQL 쿼리를 검토하십시오. | Microsoft Docs"
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
  - "Review SQL queries for security vulnerabilities"
  - "ReviewSqlQueriesForSecurityVulnerabilities"
  - "CA2100"
helpviewer_keywords: 
  - "CA2100"
  - "ReviewSqlQueriesForSecurityVulnerabilities"
ms.assetid: 79670604-c02a-448d-9c0e-7ea0120bc5fe
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2100: 보안상 취약한 부분이 있는지 SQL 쿼리를 검토하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ReviewSqlQueriesForSecurityVulnerabilities|  
|CheckId|CA2100|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드가 메서드에 대한 문자열 인수로부터 만들어진 문자열을 사용하여 <xref:System.Data.IDbCommand.CommandText%2A?displayProperty=fullName> 속성을 설정합니다.  
  
## 규칙 설명  
 이 규칙에서는 문자열 인수에 사용자 입력이 포함된 것으로 가정합니다.  사용자 입력으로부터 만들어진 SQL 명령 문자열은 SQL 삽입 공격에 취약합니다.  SQL 삽입 공격을 수행하는 악의적 사용자는 내부 데이터베이스에 무단으로 액세스하거나 내부 데이터베이스를 손상시키기 위해 쿼리의 디자인을 변경하는 입력을 제공합니다.  이러한 일반적인 기술에는 SQL 리터럴 문자열 구분 기호인 작은따옴표나 아포스트로피, SQL 주석을 나타내는 두 개의 대시, 새 명령이 시작됨을 나타내는 세미콜론을 삽입하는 것이 포함됩니다.  사용자 입력이 쿼리의 일부여야 하는 경우 효과가 큰 순서로 나열한 다음 방법 중 하나를 사용하여 공격의 위험을 줄여야 합니다.  
  
-   저장 프로시저를 사용합니다.  
  
-   매개 변수가 있는 명령 문자열을 사용합니다.  
  
-   명령 문자열을 만들기 전에 사용자 입력의 형식과 내용 모두에 대해 유효성 검사를 수행합니다.  
  
 다음 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 형식은 <xref:System.Data.IDbCommand.CommandText%2A> 속성을 구현하거나 문자열 인수를 사용하여 속성을 설정하는 생성자를 제공합니다.  
  
-   <xref:System.Data.Odbc.OdbcCommand?displayProperty=fullName> 및 <xref:System.Data.Odbc.OdbcDataAdapter?displayProperty=fullName>  
  
-   <xref:System.Data.OleDb.OleDbCommand?displayProperty=fullName> 및 <xref:System.Data.OleDb.OleDbDataAdapter?displayProperty=fullName>  
  
-   <xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName> 및 <xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>  
  
-   [System.Data.SqlServerCe.SqlCeCommand](assetId:///System.Data.SqlServerCe.SqlCeCommand?qualifyHint=False&autoUpgrade=True) 및 [System.Data.SqlServerCe.SqlCeDataAdapter](assetId:///System.Data.SqlServerCe.SqlCeDataAdapter?qualifyHint=False&autoUpgrade=True)  
  
-   <xref:System.Data.SqlClient.SqlCommand?displayProperty=fullName> 및 <xref:System.Data.SqlClient.SqlDataAdapter?displayProperty=fullName>  
  
 ToString 메서드 형식을 명시적이거나 암시적으로 사용하여 쿼리 문자열을 생성할 때 이 규칙이 위반됩니다.  예를 들면 다음과 같습니다.  
  
```  
int x = 10;  
string query = "SELECT TOP " + x.ToString() + " FROM Table";  
```  
  
 악의적인 사용자가 ToString\(\) 메서드를 무시할 수 있으므로 규칙이 위반됩니다.  
  
 또한 규칙은 ToString이 암시적으로 사용될 때 위반됩니다.  
  
```  
int x = 10;  
string query = String.Format("SELECT TOP {0} FROM Table", x);  
```  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 매개 변수가 있는 쿼리를 사용합니다.  
  
## 경고를 표시하지 않는 경우  
 명령 텍스트에 사용자 입력이 포함되지 않는 경우 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 규칙을 위반하는 `UnsafeQuery` 메서드와 매개 변수가 있는 명령 문자열을 사용하여 규칙을 충족하는 `SaferQuery` 메서드를 보여 줍니다.  
  
 [!code-vb[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/VisualBasic/ca2100-review-sql-queries-for-security-vulnerabilities_1.vb)]
 [!code-cs[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CSharp/ca2100-review-sql-queries-for-security-vulnerabilities_1.cs)]
 [!code-cpp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CPP/ca2100-review-sql-queries-for-security-vulnerabilities_1.cpp)]  
  
## 참고 항목  
 [보안 개요](../Topic/Security%20Overview2.md)