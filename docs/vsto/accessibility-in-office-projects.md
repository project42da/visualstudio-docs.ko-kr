---
title: "Office 프로젝트의 내게 필요한 옵션 | Microsoft Docs"
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
  - "액세스 가능성[Visual Studio에서 Office 개발]"
  - "Visual Studio에서 Office 개발, 액세스 가능성"
  - "리본[Visual Studio에서 Office 개발], 바로 가기 키"
  - "바로 가기 키[Visual Studio에서 Office 개발]"
ms.assetid: 48efcf1f-ca49-47ce-99f0-cc99f051aeae
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 23
---
# Office 프로젝트의 내게 필요한 옵션
  Microsoft Visual Studio 및 Microsoft Office에는 내게 필요한 옵션의 표준 요구 사항에 맞게 사용자 지정 솔루션을 빌드할 수 있는 내게 필요한 옵션 기능이 여러 가지 있습니다.  Microsoft에서는 웹에 내게 필요한 옵션 지침을 게시합니다.  자세한 내용은 [Accessibility 웹 사이트](http://go.microsoft.com/fwlink/?LinkID=37113)를 참조하십시오.  
  
 대부분의 경우 Visual Studio의 Office 프로젝트는 내게 필요한 옵션 표준을 충족하거나, 솔루션에서 내게 필요한 옵션 기능을 사용할 수 있도록 하기 위해 설정할 수 있는 속성을 노출합니다.  그러나 일부 기능의 경우에는 내게 필요한 옵션이 제한되어 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## 디자인 타임의 내게 필요한 옵션  
  
### 문서 수준 프로젝트에서 바로 가기 키 사용  
 Microsoft Office Word 문서나 Microsoft Office Excel 통합 문서가 Visual Studio에서 열려 있는 경우 한 번에 하나의 응용 프로그램에서만 바로 가기 키 명령을 받습니다.  기본적으로는 Visual Studio에서 모든 바로 가기 키 명령을 받지만 **옵션** 대화 상자의 **키보드 설정** 페이지에서 **동적 키보드 구성표**를 선택하여 문서에 포커스가 있을 때 Word나 Excel에서 바로 가기 키 명령을 받도록 할 수 있습니다.  자세한 내용은 [옵션 대화 상자, Microsoft Office 키보드 설정, Microsoft Office Word 키보드](../vsto/microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md) 및 [옵션 대화 상자, Microsoft Office 키보드 설정, Microsoft Office Excel 키보드](../vsto/microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md)를 참조하십시오.  
  
### 문서 수준 프로젝트에서 리본 메뉴의 바로 가기 키 표시  
 Word 문서나 Excel 통합 문서가 Visual Studio에서 열려 있는 경우에는 Alt 키를 눌러도 리본 메뉴의 탭 및 컨트롤에 대한 바로 가기 키를 볼 수 없습니다.  문서 또는 통합 문서가 디자이너에서 열려 있는 동안 바로 가기 키를 보려면 다음 단계를 수행합니다.  
  
##### 디자이너에서 리본 메뉴 탭 및 컨트롤의 바로 가기 키를 보려면  
  
1.  Visual Studio의 **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **Office 도구** 노드를 확장하고 **Microsoft Office Excel 키보드** 또는 **Microsoft Office Word 키보드**를 적절하게 선택합니다.  
  
3.  **동적 키보드 구성표**를 선택합니다.  
  
     변경 내용을 적용하려면 Visual Studio를 다시 시작해야 한다는 메시지가 표시됩니다.  
  
4.  **확인**을 클릭합니다.  
  
5.  Visual Studio를 다시 시작하고 프로젝트를 다시 엽니다.  
  
6.  프로젝트의 문서 또는 통합 문서 디자이너를 엽니다.  
  
7.  F6 키를 눌러 리본 메뉴의 바로 가기 키를 표시합니다.  
  
## 런타임의 내게 필요한 옵션  
  
### Office 문서의 Windows Forms 컨트롤  
 Windows Forms 컨트롤은 화면 판독기와 같은 내게 필요한 옵션 보조 도구에 대한 컨트롤 관련 정보를 제공할 수 있도록 내게 필요한 옵션 속성을 노출합니다.  문서 수준 사용자 지정의 Office 문서에 해당 컨트롤이 있을 때 이러한 내게 필요한 옵션 속성을 사용할 수 있습니다.  자세한 내용은 [Windows Form의 컨트롤에 내게 필요한 옵션 정보 제공](http://msdn.microsoft.com/library/887dee6f-5059-4d57-957d-7c6fcd4acb10)을 참조하십시오.  
  
 그러나 Windows Forms 컨트롤이 Excel 통합 문서 또는 Word 문서에서 호스팅될 때는 런타임에 내게 필요한 옵션에 대한 약간의 제한 사항이 있습니다.  
  
-   컨트롤 간에 Tab 키로 이동할 수 없습니다.  
  
-   문서의 확대\/축소 설정을 100% 이외의 값으로 변경하면 문서에서 컨트롤을 사용할 수 없게 됩니다.  
  
 문서의 Windows Forms 컨트롤 관련 제한 사항에 대한 자세한 내용은 [Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)을 참조하십시오.  
  
### 작업 창\(Actions Pane\) 및 사용자 지정 작업 창\(Task Pane\)  
 작업 창\(Actions Pane\) 또는 사용자 지정 작업 창\(Task Pane\)에 포커스가 있을 때 Windows Forms 응용 프로그램의 컨트롤에 액세스할 때와 동일한 방식으로 컨트롤에 액세스할 수 있습니다.  작업창과 문서 간에 커서를 이동하려면 **F6** 키를 누르면 됩니다.  
  
 작업 창 및 사용자 지정 작업 창에 대한 자세한 내용은 [작업 창 개요](../vsto/actions-pane-overview.md) 및 [사용자 지정 작업 창](../vsto/custom-task-panes.md)를 참조하십시오.  
  
### 디스플레이 모드  
 Visual Studio의 디스플레이 모드에는 다음과 같은 제한 사항이 있습니다.  
  
-   Word 문서나 Excel 통합 문서의 확대\/축소 설정을 100% 이외의 값으로 변경하면 해당 문서에서 컨트롤을 사용할 수 없게 됩니다.  
  
-   컴퓨터에서 내게 필요한 옵션을 **고대비 사용**으로 변경하면 **새 프로젝트** 대화 상자에 컨트롤이 제대로 표시되지 않습니다.  
  
 돋보기를 사용하여 이러한 제한 사항을 해결할 수 있습니다.  돋보기는 Windows에서 화면의 확대된 부분이 표시되는 별도의 창을 만드는 디스플레이 유틸리티입니다.  
  
## 참고 항목  
 [Office 솔루션 개발](../vsto/developing-office-solutions.md)   
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [장애인을 위한 내게 필요한 옵션](../ide/reference/accessibility-for-people-with-disabilities.md)   
 [Visual Studio의 내게 필요한 옵션](../ide/reference/accessibility-features-of-visual-studio.md)  
  
  