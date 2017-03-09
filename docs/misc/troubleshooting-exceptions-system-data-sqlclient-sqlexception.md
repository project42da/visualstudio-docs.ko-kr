---
title: "예외 문제 해결: System.Data.SqlClient.SqlException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "SqlException 클래스"
ms.assetid: 05f63457-3825-4541-ae09-0c771eb5ba35
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Data.SqlClient.SqlException
<xref:System.Data.SqlClient.SqlException> 예외는 SQL Server에서 경고나 오류를 반환할 때 생성됩니다.  
  
## 관련 팁  
 **올바른 자격 증명과 연결하고 있는지 확인하십시오.**  
 입력한 자격 증명이 유효한지 확인합니다. 자세한 내용은 [How to: Access SQL Server Using Predetermined Credentials](../Topic/How%20to:%20Access%20SQL%20Server%20Using%20Predetermined%20Credentials.md)을 참조하세요.  
  
 **서버 이름이 올바르며 서버가 실행 중인지 확인하십시오.**  
 올바른 서버 이름을 사용하고 있으며 이 서버에 도달할 수 있는지 확인합니다.  
  
### 설명  
 이 예외는 서버에서 생성된 오류를 .NET Framework Data Provider for SQL Server가 발견할 때마다 throw됩니다.  
  
 심각도가 10 이하인 메시지는 정보를 전달하기 위한 것이며 사용자가 정보를 잘못 입력하여 문제가 발생했음을 의미합니다. 11에서 16까지의 심각도는 사용자의 잘못으로 생성되며 사용자가 수정할 수 있는 문제를 나타냅니다. 17에서 25까지의 심각도는 소프트웨어나 하드웨어 오류를 나타냅니다. 심각도가 17, 18 또는 19인 오류가 발생하면 특정 문을 실행할 수는 없더라도 작업을 계속 진행할 수 있습니다.  
  
 심각도가 19 이하인 경우 <xref:System.Data.SqlClient.SqlConnection>은 열린 상태를 유지합니다. 심각도 수준이 20 이상일 때, 일반적으로 서버는 <xref:System.Data.SqlClient.SqlConnection>을 닫습니다. 그러나 사용자는 연결을 다시 열고 계속할 수 있습니다. 두 경우 모두 명령을 실행하는 메서드에서 <xref:System.Data.SqlClient.SqlException>을 생성합니다.  
  
 SQL Server에서 전달되는 경고와 정보 메시지에 대한 자세한 내용은 SQL Server 온라인 설명서에서 문제 해결 관련 단원을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Data.SqlClient.SqlException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [How to: Access SQL Server Using Predetermined Credentials](../Topic/How%20to:%20Access%20SQL%20Server%20Using%20Predetermined%20Credentials.md)