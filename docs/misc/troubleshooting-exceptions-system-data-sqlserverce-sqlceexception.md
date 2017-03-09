---
title: "예외 문제 해결: System.Data.SqlServerCe.SqlCeException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "System.Data.SqlServerCe.SqlCeException 예외"
  - "SqlCeException 예외"
  - "SqlServerCe.SqlCeException 예외"
ms.assetid: b0414ab9-94f1-48cc-a2ee-763c005150d5
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Data.SqlServerCe.SqlCeException
기본 공급자가 SQL Server Compact 데이터 소스에서 경고나 오류를 반환하는 경우 `System.Data.SqlServerCe.SqlCeException` 예외가 throw됩니다. 이 오류의 원인에 대한 자세한 내용은 MSDN 웹 사이트에서 [SQL Server Compact Edition 오류](http://msdn2.microsoft.com/library/ms171849.aspx)를 참조하세요.  
  
## 주의  
 `System.Data.SqlServerCe.SqlCeException`에는 항상 `System.Data.SqlServerCe.SqlCeError` 인스턴스가 하나 이상 포함됩니다. 이 클래스는 상속될 수 없습니다.  
  
 자세한 내용은 [SQL Server Compact 3.5 클래스 라이브러리](http://go.microsoft.com/fwlink/?LinkID=102595)를 참조하세요.  
  
## 참고 항목  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)