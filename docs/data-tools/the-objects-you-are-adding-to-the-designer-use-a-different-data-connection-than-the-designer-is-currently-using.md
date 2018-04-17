---
title: 디자이너에 추가 하려는 개체가 디자이너에서 현재 사용 중인 것 보다 다른 데이터 연결을 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c738a9beb0f2807a186a7c8b8e3f7138c82c9bfa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="the-objects-you-are-adding-to-the-designer-use-a-different-data-connection-than-the-designer-is-currently-using"></a>디자이너에 추가하려는 개체가 현재 디자이너가 사용 중인 것과 다른 데이터 연결을 사용합니다.
디자이너에 추가하려는 개체가 디자이너에서 현재 사용 중인 데이터 연결이 아닌 다른 데이터 연결을 사용합니다. 디자이너에서 사용 중인 연결을 바꾸시겠습니까?  
  
 항목을 추가 하는 경우는 [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]), 모든 항목은 하나의 공유 데이터 연결을 사용 합니다. 디자인 화면에는 화면의 모든 개체에 대해 하나의 연결을 사용하는 <xref:System.Data.Linq.DataContext>가 표시됩니다. 디자이너에서 현재 사용하는 데이터 연결과 다른 데이터 연결을 사용하는 디자이너에 개체를 추가하면 이 메시지가 나타납니다. 이 오류를 해결하려면 기존 연결 유지를 선택하세요. 이 항목을 선택하면 선택한 개체가 추가되지 않습니다. 또한 개체를 추가 하 고 다시 설정 하려면 수도 <xref:System.Data.Linq.DataContext> 새 연결에 연결 합니다.  
  
> [!NOTE]
>  클릭 하면 **예**의 모든 엔터티 클래스가 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 새 연결에 매핑됩니다.  
  
### <a name="to-replace-the-existing-connection-with-the-connection-used-by-the-selected-object"></a>기존 연결을 선택한 개체에서 사용하는 연결로 대체하려면  
  
-   **예**를 클릭합니다.  
  
     선택한 개체가 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 추가되고 DataContext.Connection이 새 연결로 설정됩니다.  
  
### <a name="to-continue-to-use-the-existing-connection-and-cancel-adding-the-selected-object"></a>기존 연결을 계속 사용하고 선택한 개체 추가를 취소하려면  
  
-   **아니요**를 클릭합니다.  
  
     작업이 취소됩니다.  DataContext.Connection이 기존 연결로 설정됩니다.  
  
## <a name="see-also"></a>참고자료
[O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)  
[Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
 