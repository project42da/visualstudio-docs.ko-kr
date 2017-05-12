---
title: "방법: 응용 프로그램에 사용자 지정 작업 창 추가"
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
  - "사용자 지정 작업 창[Visual Studio에서 Office 개발], 응용 프로그램에 추가"
  - "작업 창[Visual Studio에서 Office 개발], 응용 프로그램에 추가"
ms.assetid: 67b4ed5b-d77e-4630-b851-34bb25bdc9b3
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# 방법: 응용 프로그램에 사용자 지정 작업 창 추가
  VSTO 추가 기능을 사용하여 위에 나열된 응용 프로그램에 사용자 지정 작업창을 추가할 수 있습니다.  자세한 내용은 [사용자 지정 작업 창](../vsto/custom-task-panes.md)를 참조하세요.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## 응용 프로그램에 사용자 지정 작업창 추가  
  
#### 응용 프로그램에 사용자 지정 작업창을 추가하려면  
  
1.  위에 나열된 응용 프로그램 중 하나에 대한 VSTO 추가 기능 프로젝트를 열거나 만듭니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
2.  **프로젝트** 메뉴에서 **사용자 정의 컨트롤 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자에서 새 사용자 정의 컨트롤의 이름을 **MyUserControl**로 변경하고 **추가**를 클릭합니다.  
  
     사용자 정의 컨트롤이 디자이너에서 열립니다.  
  
4.  **도구 상자**에서 하나 이상의 Windows Forms 컨트롤을 사용자 정의 컨트롤에 추가합니다.  
  
5.  **ThisAddIn.cs** 또는 **ThisAddIn.vb** 코드 파일을 엽니다.  
  
6.  `ThisAddIn` 클래스에 다음 코드를 추가합니다.  이 코드는 `MyUserControl` 및 <xref:Microsoft.Office.Tools.CustomTaskPane>의 인스턴스를 `ThisAddIn` 클래스의 멤버로 선언합니다.  
  
     [!code-csharp[Trin_TaskPaneBasic#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_TaskPaneBasic/CS/ThisAddIn.cs#1)]
     [!code-vb[Trin_TaskPaneBasic#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_TaskPaneBasic/VB/ThisAddIn.vb#1)]  
  
7.  다음 코드를 `ThisAddIn_Startup` 이벤트 처리기에 추가합니다.  이 코드는 `CustomTaskPanes` 컬렉션에 `MyUserControl` 개체를 추가하여 새 <xref:Microsoft.Office.Tools.CustomTaskPane>을 만듭니다.  코드에서 작업창도 표시합니다.  
  
     [!code-csharp[Trin_TaskPaneBasic#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_TaskPaneBasic/CS/ThisAddIn.cs#2)]
     [!code-vb[Trin_TaskPaneBasic#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_TaskPaneBasic/VB/ThisAddIn.vb#2)]  
  
    > [!NOTE]  
    >  이 코드는 응용 프로그램의 활성 창과 사용자 지정 작업창을 연결합니다.  일부 응용 프로그램의 경우 작업창이 응용 프로그램의 다른 문서나 항목과 함께 표시되도록 이 코드를 수정하는 것이 좋습니다.  자세한 내용은 [사용자 지정 작업 창](../vsto/custom-task-panes.md)를 참조하세요.  
  
## 참고 항목  
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [사용자 지정 작업 창](../vsto/custom-task-panes.md)   
 [연습: 사용자 지정 작업 창을 사용하여 응용 프로그램 자동화](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)  
  
  