---
title: "TableAdapter를 사용 하 여 데이터를 업데이트 | Microsoft Docs"
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
- data [Visual Studio], saving
- data [Visual Studio], TableAdapters
- updating data, TableAdapters
- TableAdapters, updating data
- data [Visual Studio], updating
- saving data
ms.assetid: 5e32e10e-9bac-4969-9bdd-b8f6919d3516
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 4968eab5e1d355543a8658e72540bc66fa2543b9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="update-data-by-using-a-tableadapter"></a>TableAdapter를 사용 하 여 데이터 업데이트
데이터 집합의 데이터를 수정 하 고 유효성을 검사 된 후 보낼 수 있습니다 업데이트 된 데이터를 데이터베이스에 다시 호출 하 여는 `Update` 의 메서드는 [TableAdapter](../data-tools/create-and-configure-tableadapters.md)합니다. `Update` 메서드는 단일 데이터 테이블을 업데이트 하 고 올바른 명령 (INSERT, UPDATE 또는 DELETE)에 따라 실행 되는 <xref:System.Data.DataRow.RowState%2A> 테이블의 각 데이터 행입니다. 데이터 집합에는 관련 테이블을 사용 하 여 업데이트를 수행 하는 TableAdapterManager 클래스를 생성 됩니다. TableAdapterManager 클래스를 사용 하면 업데이트 데이터베이스에 정의 된 외래 키 제약 조건에 따라 올바른 순서로 수행 됩니다. 데이터 바인딩된 컨트롤을 사용 하면 데이터 바인딩 아키텍처 tableAdapterManager 호출 되는 TableAdapterManager 클래스의 멤버 변수를 만듭니다. 
  
> [!NOTE]
>  데이터 소스는 데이터 집합의 내용으로 업데이트 하려고 할 때 오류가 발생할 수 있습니다. 오류를 방지 하려면 두 어댑터의 호출 하는 코드는 권장 `Update` 내에서 메서드는 `try` / `catch` 블록입니다.  
  
 데이터 소스를 업데이트 하기 위한 정확한 절차를 비즈니스 요구에 따라 다르지만 단계는 다음과 같습니다.  
  
1.  어댑터의 호출 `Update` 에서 메서드는 `try` / `catch` 블록입니다.  
  
2.  예외가 포착 되는 오류를 일으킨 데이터 행을 찾습니다. 
  
3.  데이터의 문제 (가능한 경우 프로그래밍 방식으로 또는 수정에 대 한 사용자에 게 잘못 된 행을 제공 하 여) 행을 한 다음 다시 업데이트 (<xref:System.Data.DataRow.HasErrors%2A>, <xref:System.Data.DataTable.GetErrors%2A>).  
  
## <a name="save-data-to-a-database"></a>데이터베이스에 데이터를 저장 합니다.  
 호출 된 `Update` TableAdapter의 합니다. 데이터베이스에 기록 되도록 값을 포함 하는 데이터 테이블의 이름을 전달 합니다.  
  
#### <a name="to-update-a-database-by-using-a-tableadapter"></a>TableAdapter를 사용 하 여 데이터베이스를 업데이트 하려면  
  
-   TableAdapter의 묶습니다`Update` 에서 메서드는 `try` / `catch` 블록입니다. 내용을 업데이트 하는 방법을 보여 주는 다음 예제는 `Customers` 테이블에 `NorthwindDataSet` 내에서 한 `try` / `catch` 블록입니다.  
  
     [!code-csharp[VbRaddataSaving#9](../data-tools/codesnippet/CSharp/update-data-by-using-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataSaving#9](../data-tools/codesnippet/VisualBasic/update-data-by-using-a-tableadapter_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)