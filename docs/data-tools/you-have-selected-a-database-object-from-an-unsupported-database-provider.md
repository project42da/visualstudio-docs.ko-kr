---
title: "데이터베이스 개체는 지원 되지 않는 데이터베이스 공급자에서 선택 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 05e638be5cc11f66052e5a1f6116e7205b824106
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>지원되지 않는 데이터베이스 공급자에서 데이터베이스 공급자를 선택했습니다.
O/R 디자이너는는.NET Framework Data Provider for SQL Server 지원 (<xref:System.Data.SqlClient>). 클릭할 수 있지만 **확인** 하며 지원 되지 않는 데이터베이스 공급자의에서 개체를 작성 하려면 계속 하기, 실행 시 예기치 않은 동작이 발생할 수 있습니다.  
  
> [!NOTE]
>  .NET Framework Data Provider for SQL Server를 사용하는 데이터 연결만 지원됩니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- **확인**을 클릭합니다.

   지원 되지 않는 데이터베이스 공급자를 사용 하는 연결에 매핑되는 엔터티 클래스를 디자인을 계속할 수 있습니다. 지원되지 않는 데이터베이스 공급자를 사용하면 예상치 못한 동작이 발생할 수도 있습니다.  
  
     또는  
  
- 클릭 **취소**합니다.

   작업이 중지됩니다. .NET Framework Provider for SQL Server를 사용하는 데이터 연결을 만들거나 사용합니다.  
  
## <a name="see-also"></a>참고 항목
[O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)  
[Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)