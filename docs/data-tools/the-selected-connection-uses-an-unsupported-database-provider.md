---
title: "선택한 연결에서 지원되지 않는 데이터베이스 공급자를 사용하고 있습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
caps.latest.revision: 3
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 선택한 연결에서 지원되지 않는 데이터베이스 공급자를 사용하고 있습니다.
이 메시지는 .NET Framework Data Provider for SQL Server를 사용하지 않는 항목을 **서버 탐색기**\/**데이터베이스 탐색기**에서 [O\/R 디자이너\(개체 관계형 디자이너\)](../data-tools/linq-to-sql-tools-in-visual-studio2.md)로 끌어 오는 경우 나타납니다.  
  
 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서는 .NET Framework Provider for SQL Server를 사용하는 데이터 연결만 지원합니다.Microsoft SQL Server 또는 Microsoft SQL Server 데이터베이스 파일에 대한 연결만 유효합니다.  
  
### 이 오류를 해결하려면  
  
-   .NET Framework Data Provider for SQL Server를 사용하는 데이터 연결의 항목만 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 추가합니다.  
  
## 참고 항목  
 <xref:System.Data.SqlClient>   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [How to: Create Connections to SQL Server Databases](http://msdn.microsoft.com/ko-kr/360c340d-e5a6-4a7e-a569-e95d500be43d)   
 [.NET Framework 데이터 공급자](../Topic/.NET%20Framework%20Data%20Providers.md)   
 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)   
 [데이터 응용 프로그램 만들기](../data-tools/creating-data-applications.md)