---
title: "오류: 사용자는 sp_enable_sql_debug 저장 프로시저를 실행할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.sqlde_accessdenied"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 11957495-c238-4cc5-8937-e4026f5e10e1
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# 오류: 사용자는 sp_enable_sql_debug 저장 프로시저를 실행할 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

저장 프로시저 sp\_enable\_sql\_debug를 서버에서 실행할 수 없는 경우입니다.  이 오류의 원인은 다음과 같습니다.  
  
-   연결에 문제가 있는 경우입니다.  서버에 안정적으로 연결되어 있어야 합니다.  
  
-   서버에 대해 필요한 권한이 없는 경우입니다.  SQL Server 2005에서 디버깅하려면 Visual Studio를 실행하는 데 사용되는 계정과 SQL Server에 연결하는 데 사용되는 계정이 모두 sysadmin 역할의 멤버여야 합니다.  SQL Server에 연결하는 데 사용한 계정이 Windows 사용자 계정\(Windows 인증을 사용하는 경우\)이거나 사용자 ID와 암호로 지정된 계정\(SQL 인증을 사용하는 경우\)입니다.  
  
 자세한 내용은 [How to: Set SQL Server Permissions for Debugging](http://msdn.microsoft.com/ko-kr/84e088d0-0409-41d4-841b-f5d4b0fda414)을 참조하십시오.  
  
## 참고 항목  
 [How to: Set SQL Server Permissions for Debugging](http://msdn.microsoft.com/ko-kr/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Setting Up SQL Debugging](http://msdn.microsoft.com/ko-kr/3db09e68-edcc-42de-9c22-4e97cfd55ab3)