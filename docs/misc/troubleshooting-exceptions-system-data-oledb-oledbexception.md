---
title: "예외 문제 해결: System.Data.OleDb.OleDbException | Microsoft Docs"
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
  - "OLEDB"
  - "OleDbException 클래스"
  - "예외, OLEDB"
ms.assetid: f50077cf-e411-41f0-b73e-19eef83036c1
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Data.OleDb.OleDbException
<xref:System.Data.OleDb.OleDbException> 예외는 OLE DB 데이터 소스에서 경고나 오류를 반환할 때 생성됩니다.  
  
## 관련 팁  
 **올바른 자격 증명과 연결하고 있는지 확인하세요.**  
 입력한 자격 증명이 유효한지 확인합니다. 자세한 내용은 <xref:System.Data.OleDb.OleDbErrorCollection>을 참조하세요.  
  
 **서버 이름이 올바르며 서버가 실행 중인지 확인하세요.**  
 올바른 서버 이름을 사용하고 있으며 이 서버에 도달할 수 있는지 확인합니다. 자세한 내용은 <xref:System.Data.OleDb.OleDbErrorCollection>을 참조하세요.  
  
### 설명  
 이 예외는 서버에서 생성된 오류를 .NET Framework Data Provider for OLE DB가 발견할 때마다 throw됩니다.  
  
 오류의 심각도가 너무 높으면 서버에서 <xref:System.Data.OleDb.OleDbConnection>이 닫힐 수 있습니다. 그러나 사용자는 연결을 다시 열고 계속할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Data.OleDb.OleDbException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)