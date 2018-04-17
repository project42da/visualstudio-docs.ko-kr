---
title: DataContext 메서드의 반환 형식 변경은 취소할 수 없습니다 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 76b161fc-5075-4192-8d94-f15b02e199e9
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 154dfd76cb1fbd7fb3af7eaa204ece59d8803f35
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="changing-the-return-type-of-a-datacontext-method-cannot-be-undone"></a>DataContext 메서드의 반환 형식 변경은 취소할 수 없습니다.
DataContext 메서드의 반환 형식을 변경하면 실행 취소할 수 없습니다. 자동으로 생성된 형식으로 되돌리려면 항목을 서버 탐색기/데이터베이스 탐색기에서 O/R 디자이너로 끌어 와야 합니다. 반환 형식을 변경하시겠습니까?  
  
<xref:System.Data.Linq.DataContext> 메서드의 반환 형식은 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 항목을 놓는 위치에 따라 달라집니다. 항목을 기존 엔터티 클래스에 직접 놓으면 엔터티 클래스의 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 항목을 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 빈 영역에 놓으면 자동으로 생성된 형식을 반환하는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 메서드 창에 추가한 후 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 변경할 수 있습니다. 반환 형식을 검사 하거나 변경 하는 <xref:System.Data.Linq.DataContext> 메서드를 선택 하 고 클릭는 **반환 형식** 속성에는 **속성** 창.  
  
### <a name="to-change-the-return-type-of-a-datacontext"></a>DataContext의 반환 형식을 변경하려면  
  
-   **예**를 클릭합니다.  
  
### <a name="to-exit-the-message-box-and-leave-the-return-type-unchanged"></a>반환 형식을 변경하지 않고 메시지 상자를 끝내려면  
  
-   **아니요**를 클릭합니다.  
  
### <a name="to-revert-to-the-original-return-type-after-changing-the-return-type"></a>반환 형식을 변경한 후 원래 반환 형식으로 되돌리려면  
  
1.  선택 된 <xref:System.Data.Linq.DataContext> 메서드를는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 하 고 삭제 합니다.  
  
2.  항목을 찾아 **서버 탐색기/데이터베이스 탐색기** 로 끌어 옵니다는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다.  
  
    원래 기본 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다.  
  
## <a name="see-also"></a>참고자료
[O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)  
[Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)