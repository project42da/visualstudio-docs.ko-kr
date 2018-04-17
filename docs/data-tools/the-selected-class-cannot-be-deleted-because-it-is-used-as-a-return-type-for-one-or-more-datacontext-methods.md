---
title: 선택한 클래스가 하나 이상의 DataContext 메서드의 반환 형식으로 사용 되므로 삭제할 수 없습니다 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0b5781508083524a5cf7374a12fd962f0fe34aaf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>선택한 클래스가 하나 이상의 DataContext 메서드의 반환 형식으로 사용되므로 해당 클래스를 삭제할 수 없습니다.
하나 이상의 <xref:System.Data.Linq.DataContext> 메서드 반환 형식은 선택한 엔터티 클래스입니다. <xref:System.Data.Linq.DataContext> 메서드의 반환 형식으로 사용되는 엔터티 클래스를 삭제하면 프로젝트를 컴파일할 수 없습니다. 선택한 엔터티 클래스를 삭제하려면 해당 엔터티 클래스를 사용하는 <xref:System.Data.Linq.DataContext> 메서드를 식별하고 해당 메서드의 반환 형식을 서로 다른 엔터티 클래스로 설정합니다.  
  
 반환 형식으로 되돌리려면 <xref:System.Data.Linq.DataContext> 원래 자동으로 생성 된 형식으로 하는 메서드를 먼저 삭제는 <xref:System.Data.Linq.DataContext> 메서드 창에 있는 메서드의 한 다음에서 개체를 끌어 **서버 탐색기** / **데이터베이스 탐색기** 에서 O/R 디자이너로 다시 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  식별 <xref:System.Data.Linq.DataContext> 선택 하 여 반환 형식이 엔터티 클래스를 사용 하는 메서드는 <xref:System.Data.Linq.DataContext> 메서드에 메서드 창 및 검사는 **반환 형식** 속성에는 **속성** 창 .  
  
2.  설정의 **반환 형식** 서로 다른 엔터티 클래스로 또는 삭제에는 <xref:System.Data.Linq.DataContext> 메서드 창에서 메서드.  
  
## <a name="see-also"></a>참고자료
[O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)  
[Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)