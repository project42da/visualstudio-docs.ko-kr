---
title: "방법: 트랜잭션을 사용하여 데이터 저장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터[Visual Studio], 저장"
  - "데이터 저장, 트랜잭션 사용"
  - "System.Transactions 네임스페이스"
  - "트랜잭션, 데이터 저장"
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 트랜잭션을 사용하여 데이터 저장
<xref:System.Transactions> 네임스페이스를 사용하여 데이터를 트랜잭션에 저장합니다.  <xref:System.Transactions.TransactionScope> 개체를 사용하면 자동으로 관리되는 트랜잭션에 참여할 수 있습니다.  
  
 프로젝트가 만들어질 때 System.Transactions 어셈블리에 대한 참조가 없으므로 트랜잭션을 사용하는 프로젝트에 참조를 수동으로 추가해야 합니다.  
  
> [!NOTE]
>  <xref:System.Transactions> 네임스페이스는 Windows 2000 버전 이상에서 지원됩니다.  
  
 트랜잭션을 구현하는 가장 쉬운 방법은 `using` 문에서 <xref:System.Transactions.TransactionScope> 개체를 인스턴스화하는 것입니다.  \(자세한 내용은 [Using Statement](/dotnet/visual-basic/language-reference/statements/using-statement) 및 [using 문](/dotnet/csharp/language-reference/keywords/using-statement)을 참조하십시오. `using` 문 내에서 실행된 코드는 트랜잭션에 참여하게 됩니다.  
  
 트랜잭션을 커밋하려면 <xref:System.Transactions.TransactionScope.Complete%2A> 메서드를 using 블록의 마지막 문으로 호출합니다.  
  
 트랜잭션을 롤백하려면 <xref:System.Transactions.TransactionScope.Complete%2A> 메서드를 호출하기 전에 예외를 throw합니다.  
  
 자세한 내용은 [연습: 트랜잭션에 데이터 저장](../data-tools/save-data-in-a-transaction.md)을 참조하십시오.  
  
### System.Transactions dll에 참조를 추가하려면  
  
1.  **프로젝트** 메뉴에서 **참조 추가**를 선택합니다.  
  
2.  **.NET** 탭\(SQL Server 프로젝트의 경우 **SQL Server** 탭\)에서 **System.Transactions**를 선택하고 **확인**을 클릭합니다.  
  
     System.Transactions.dll에 대한 참조가 프로젝트에 추가됩니다.  
  
### 트랜잭션에 데이터를 저장하려면  
  
-   코드를 추가하여 트랜잭션이 포함된 using 문 내에 데이터를 저장합니다.  다음 코드에서는 using 문에서 <xref:System.Transactions.TransactionScope> 개체를 만들고 인스턴스화하는 방법을 보여 줍니다.  
  
     [!code-vb[VbRaddataSaving#11](../data-tools/codesnippet/VisualBasic/save-data-by-using-a-transaction_1.vb)]
     [!code-cs[VbRaddataSaving#11](../data-tools/codesnippet/CSharp/save-data-by-using-a-transaction_1.cs)]  
  
## 참고 항목  
 [연습: 트랜잭션에 데이터 저장](../data-tools/save-data-in-a-transaction.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)