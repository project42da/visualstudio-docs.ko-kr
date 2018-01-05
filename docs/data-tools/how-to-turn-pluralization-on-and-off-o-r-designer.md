---
title: "방법: 복수형 설정 및 해제 (O R 디자이너) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: a78f38d4b02311a164e0858744b70fbc5fb0ddaa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>방법: 복수형 설정 및 해제 (O/R 디자이너)
기본적으로 s 또는에서 ies 이름을 가진 데이터베이스 개체를 끌 때 **서버 탐색기**/**데이터베이스 탐색기** 에 [LINQ to SQL 도구VisualStudio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md), 생성된 된 엔터티 클래스의 이름이 복수형에서 단 수로 바뀝니다. 이렇게 하면 인스턴스화된 엔터티 클래스를 데이터의 단일 레코드에 매핑하는 것을 보다 정확하게 나타낼 수 있습니다. 예를 들어 Customers 테이블을 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 추가하면 단일 고객에 대한 데이터만 해당 클래스에 보유되므로 Customer라는 엔터티 클래스가 만들어집니다.  
  
> [!NOTE]
>  복수 적용은 기본적으로 Visual Studio 영어 버전에만 적용됩니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-turn-pluralization-on-and-off"></a>복수 적용을 설정 및 해제하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  에 **옵션** 대화 상자에서 **데이터베이스 도구**합니다.  
  
    > [!NOTE]
    >  선택 **모든 설정 표시** 경우는 **데이터베이스 도구** 노드가 표시 되지 않습니다.  
  
3.  클릭 **O/R 디자이너**합니다.  
  
4.  설정 **복수 이름 적용** 를 **Enabled** = **False** 설정 하 여 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 클래스 이름은 변경 되지 않습니다.  
  
5.  설정 **복수 이름 적용** 를 **Enabled** = **True** 복수 적용 규칙에 추가 된 개체의 클래스 이름에 적용 하는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
[LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)   
[Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)