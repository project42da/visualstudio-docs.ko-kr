---
title: "방법: Office 프로젝트의 이벤트 처리기 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Basic [Office development in Visual Studio], event handlers
- event handlers [Office development in Visual Studio]
- Visual C# [Office development in Visual Studio], event handlers
- events [Office development in Visual Studio]
ms.assetid: 2cfd6a45-4c25-4431-b4fc-e0f2c0a72e54
caps.latest.revision: "31"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: af681832a8c298427c13060d858b57b99654953a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-event-handlers-in-office-projects"></a>방법: Office 프로젝트에서 이벤트 처리기 만들기
  여러 가지 방법으로 Visual Basic 및 C#에서 이벤트 처리기를 만들 수 있습니다. 디자인 뷰에서 컨트롤을 두 번 클릭 하 여 기본 컨트롤에 대 한 이벤트 처리기를 만들 하거나 이벤트 창을 사용 하 여 수는 **속성** 창 컨트롤에 모든 이벤트에 대 한 처리기를 만들 수 있습니다. 그러나 코드 보기에 있는 경우 있습니다 하지 않을 이벤트 처리기를 만들 디자인 뷰로 전환 합니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-create-an-event-handler-in-visual-basic"></a>Visual Basic의 이벤트 처리기를 만들려면  
  
1.  **클래스 이름** 코드 편집기의 맨 위에 있는 드롭다운 목록에서 만들기에 대 한 이벤트 처리기 개체를 선택 합니다.  
  
    > [!NOTE]  
    >  에 대 한 이벤트 처리기를 만들려는 경우 `ThisDocument` 또는 `ThisWorkbook`를 선택 해야 **(ThisDocument 이벤트)** 또는 **(ThisWorkbook 이벤트)** 에 **클래스 이름**드롭 다운 목록  
  
2.  **메서드 이름** 드롭 다운 목록 맨 위에 있는 코드 편집기의 이벤트를 선택 합니다.  
  
     Visual Studio 이벤트 처리기를 만들고 새로 만든된 이벤트 처리기에 삽입 지점을 이동 합니다. 이벤트 처리기에 이미 있으면 기존 이벤트 처리기로 삽입 지점이 이동 합니다.  
  
### <a name="to-create-an-event-handler-in-c"></a>C#의 이벤트 처리기를 만들려면  
  
1.  이벤트 대리자를 만듭니다는 **시작** 뒤에 공백이 정규화 된 이벤트 이름을 입력 하 고 입력 하 여 클래스의 이벤트  **+=**  공백 없이 나중에 있습니다. 예:  
  
     `this.<object name>.<event name> +=`  
  
2.  코드 줄의 끝에 TAB 키를 두 번 누릅니다.  
  
     Visual Studio 자동으로 코드 줄을 완료, 이벤트 처리기를 만들고 새로 만든된 이벤트 처리기에 삽입 지점을 이동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)   
 [연습: NamedRange 컨트롤의 이벤트 프로그래밍](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Office 솔루션 빌드](../vsto/building-office-solutions.md)  
  
  