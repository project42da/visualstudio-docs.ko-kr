---
title: 선택한 연결에서 지원되지 않는 데이터베이스 공급자를 사용합니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 77519a5497c26553e2023862e46f3ba618e4f99f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>선택한 연결에서 지원되지 않는 데이터베이스 공급자를 사용합니다.

.NET Framework Data Provider for SQL Server에서 사용 하지 않는 항목을 끌어 올 때이 메시지가 표시 **서버 탐색기**/**데이터베이스 탐색기** 에 [LINQ to SQL Visual Studio의 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)합니다.

[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서는 .NET Framework Provider for SQL Server를 사용하는 데이터 연결만 지원합니다. Microsoft SQL Server 또는 Microsoft SQL Server 데이터베이스 파일에 대한 연결만 유효합니다.

이 오류를 해결 하려면.NET Framework Data Provider for SQL Server를 사용 하는 데이터 연결의 항목만 추가 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다.

## <a name="see-also"></a>참고자료

- <xref:System.Data.SqlClient>
- [O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)
- [Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
