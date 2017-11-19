---
title: "방법: 트랜잭션을 사용 하 여 데이터 저장 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- saving data, using transactions
- System.Transactions namespace
- transactions, saving data
- data [Visual Studio], saving
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 23cf5ee9ef7369d8c0f52adde639adad4abe3ae6
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="how-to-save-data-by-using-a-transaction"></a>방법: 트랜잭션을 사용 하 여 데이터 저장
사용 하 여 트랜잭션에서 데이터를 저장 된 <xref:System.Transactions> 네임 스페이스입니다. 사용 된 <xref:System.Transactions.TransactionScope> 개체가 자동으로 관리 되는 트랜잭션에 참여 하도록 합니다.  
  
트랜잭션을 사용 하는 프로젝트에 대 한 참조를 수동으로 추가 해야 하므로 System.Transactions 어셈블리에 대 한 참조는 프로젝트 생성 되지 않습니다.  
  
트랜잭션을 구현 하는 가장 쉬운 방법은를 인스턴스화하는 <xref:System.Transactions.TransactionScope> 개체는 `using` 문. (자세한 내용은 참조 [문을 사용 하 여](/dotnet/visual-basic/language-reference/statements/using-statement), 및 [문을 사용 하 여](/dotnet/csharp/language-reference/keywords/using-statement).) 내에서 실행 되는 코드는 `using` 문을 트랜잭션에 참여 합니다.  
  
트랜잭션을 커밋하는 호출 하는 <xref:System.Transactions.TransactionScope.Complete%2A> 사용 하 여 마지막 문으로 메서드를 차단 합니다.  
  
트랜잭션을 롤백하려면를 호출 하기 전에 예외가 throw 된 <xref:System.Transactions.TransactionScope.Complete%2A> 메서드.  
  
## <a name="to-add-a-reference-to-the-systemtransactionsdll"></a>System.Transactions.dll에 대 한 참조를 추가 하려면  
  
1.  에 **프로젝트** 메뉴 선택 **참조 추가**합니다.  
  
2.  에 **.NET** 탭 (**SQL Server** SQL Server 프로젝트에 대 한 탭)을 선택 **System.Transactions**를 선택한 후 **확인**합니다.  
  
     System.Transactions.dll에 대 한 참조는 프로젝트에 추가 됩니다.  
  
## <a name="to-save-data-in-a-transaction"></a>트랜잭션에서 데이터를 저장 하려면  
  
-   Using 내에서 데이터를 저장 하는 코드를 추가 트랜잭션이 포함 된 문입니다. 다음 코드를 만들고 인스턴스화하는 방법을 보여 줍니다는 <xref:System.Transactions.TransactionScope> 개체를 사용 하 여 문:  
  
     [!code-vb[VbRaddataSaving#11](../data-tools/codesnippet/VisualBasic/save-data-by-using-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#11](../data-tools/codesnippet/CSharp/save-data-by-using-a-transaction_1.cs)]  
  
## <a name="see-also"></a>참고 항목
[데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)  
[연습: 트랜잭션에 데이터 저장](../data-tools/save-data-in-a-transaction.md)  