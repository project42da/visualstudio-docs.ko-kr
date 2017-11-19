---
title: "이 관련 메서드는 다음과 같은 기본 삽입, 업데이트 또는 삭제 방법에 대 한 백업 메서드에 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 3f8a31f886548d03f7acac58d392713ced297b42
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>이 관련 메서드는 다음과 같은 기본 삽입, 업데이트 및 삭제 메서드를 지원하는 메서드입니다.
이 관련 메서드는 다음과 같은 기본 삽입, 업데이트 또는 삭제 메서드를 지원하는 메서드입니다. 이 관련 메서드를 삭제하면 이러한 메서드도 삭제됩니다. 계속하시겠습니까?  
  
 선택한 `DataContext` 메서드는 O/R 디자이너의 엔터티 클래스 중 하나에 대해 삽입, 업데이트 또는 삭제 메서드 중 하나가 현재 사용되고 있습니다. 선택한 메서드를 삭제하면 이 메서드를 사용하는 엔터티 클래스는 업데이트하는 동안 삽입, 업데이트 또는 삭제를 수행하는 기본 런타임 동작으로 되돌립니다.  
  
### <a name="to-delete-the-selected-method-causing-the-entity-class-to-use-runtime-updates"></a>엔터티 클래스에서 런타임 업데이트를 사용할 수 있도록 선택한 메서드를 삭제하려면  
  
-   **예**를 클릭합니다.  
  
     선택한 메서드가 삭제되고 업데이트 동작을 재정의하기 위해 이 메서드를 사용하는 모든 클래스가 기본 LINQ to SQL 런타임 동작을 사용하도록 되돌립니다.  
  
### <a name="to-close-the-message-box-leaving-the-selected-method-unchanged"></a>선택한 메서드를 변경하지 않고 메시지 상자를 닫으려면  
  
-   **아니요**를 클릭합니다.  
  
     메시지 상자가 닫히고 변경되지 않습니다.  
  
## <a name="see-also"></a>참고 항목
[O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)  
[Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)