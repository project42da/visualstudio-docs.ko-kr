---
title: "방법: Office 프로젝트에서 이벤트 처리기 만들기"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "이벤트 처리기[Visual Studio에서 Office 개발]"
  - "이벤트[Visual Studio에서 Office 개발]"
  - "Visual Basic[Visual Studio에서 Office 개발], 이벤트 처리기"
  - "Visual C#[Visual Studio에서 Office 개발], 이벤트 처리기"
ms.assetid: 2cfd6a45-4c25-4431-b4fc-e0f2c0a72e54
caps.latest.revision: 31
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 30
---
# 방법: Office 프로젝트에서 이벤트 처리기 만들기
  Visual Basic 및 C\#에서 이벤트 처리기를 만드는 데는 여러 가지 방법이 있습니다.  디자인 뷰에서 컨트롤을 두 번 클릭하여 컨트롤에 대한 기본 이벤트 처리기를 만들거나 **속성** 창의 이벤트 창을 사용하여 컨트롤의 모든 이벤트에 대한 처리기를 만들 수 있습니다.  그러나 코드 뷰에서 작업 중인 경우 이벤트 처리기를 만들기 위해 디자인 뷰로 전환하는 것은 비효율적인 방법입니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### Visual Basic에서 이벤트 처리기를 만들려면  
  
1.  코드 편집기 맨 위에 있는 **클래스 이름** 드롭다운 목록에서 이벤트 처리기를 만들 개체를 선택합니다.  
  
    > [!NOTE]  
    >  `ThisDocument` 또는 `ThisWorkbook`에 대한 이벤트 처리기를 만드는 경우에는 **클래스 이름** 드롭다운 목록에서 **\(ThisDocument 이벤트\)** 또는 **\(ThisWorkbook 이벤트\)**를 선택해야 합니다.  
  
2.  코드 편집기 맨 위에 있는 **메서드 이름** 드롭다운 목록에서 이벤트를 선택합니다.  
  
     Visual Studio에서 이벤트 처리기가 작성되고 삽입 지점이 새로 만든 이벤트 처리기로 이동합니다.  이벤트 처리기가 이미 있는 경우 삽입 지점이 기존의 이벤트 처리기로 이동합니다.  
  
### C\#에서 이벤트 처리기를 만들려면  
  
1.  정규화된 이벤트 이름을 입력하고 공백을 추가한 다음 끝에 공백이 포함되지 않은 \+\= 기호를 입력하여 클래스의 **Startup** 이벤트에서 이벤트 대리자를 만듭니다.  예를 들면 다음과 같습니다.  
  
     `this.<object name>.<event name> +=`  
  
2.  코드 줄의 끝에서 Tab 키를 두 번 누릅니다.  
  
     Visual Studio에서 코드 줄이 자동으로 완료되고 이벤트 처리기가 작성된 다음 삽입 지점이 새로 만든 이벤트 처리기로 이동합니다.  
  
## 참고 항목  
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)   
 [연습: NamedRange 컨트롤의 이벤트 프로그래밍](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Office 솔루션 빌드](../vsto/building-office-solutions.md)  
  
  