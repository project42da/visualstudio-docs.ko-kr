---
title: "Office 프로젝트의 내게 필요한 옵션 | Microsoft Docs"
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
- Office development in Visual Studio, accessibility
- shortcut keys [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], shortcut keys
- accessibility [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 567ab9cffbd4546e276fcfd55af773e99fe07d34
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="accessibility-in-office-projects"></a>Office 프로젝트의 내게 필요한 옵션
  Microsoft Visual Studio 및 Microsoft Office 내게 필요한 옵션 표준 요구 사항을 충족 하는 사용자 지정 솔루션을 구축할 수 있도록 하는 여러 접근성 기능이 포함 됩니다. Microsoft는 웹에서 내게 필요한 옵션에 대 한 지침을 게시합니다. 자세한 내용은 참조는 [내게 필요한 옵션 웹 사이트](http://go.microsoft.com/fwlink/?LinkID=37113)합니다.  
  
 대부분의 경우 Visual Studio에서 Office 프로젝트는 솔루션에 액세스할 수 있도록 설정할 수 있는 내게 필요한 옵션 표준 또는 노출 속성을 충족 합니다. 그러나 액세스 가능성 제한 된 일부 기능이 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="accessibility-at-design-time"></a>디자인 타임에 내게 필요한 옵션  
  
### <a name="using-shortcut-keys-in-document-level-projects"></a>문서 수준 프로젝트의 바로 가기 키를 사용 하 여  
 Microsoft Office Word 문서 또는 Microsoft Office Excel 통합 문서를 연 Visual Studio에서 바로 가기 키 명령을 한 번에 하나의 응용 프로그램을 받습니다. 기본적으로 Visual Studio 모든 바로 가기 키 명령을 받지만 Word 또는 Excel을 선택 하 여 문서에 포커스가 있을 때 수신 정확해 **동적 키보드 구성표** 에 **키보드 설정** 페이지 **옵션** 대화 상자. 자세한 내용은 참조 [Microsoft Office Word 키보드, Microsoft Office 키보드 설정, 옵션 대화 상자](../vsto/microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md) 및 [MicrosoftOfficeExcel키보드,MicrosoftOffice키보드설정,옵션대화상자](../vsto/microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md).  
  
### <a name="displaying-shortcut-keys-for-the-ribbon-in-document-level-projects"></a>문서 수준 프로젝트에서 리본 메뉴에 대 한 바로 가기 키 표시  
 Word 문서 또는 Excel 통합 문서를 연 Visual Studio에서 탭 및 리본 메뉴에 컨트롤에 대 한 바로 가기 키를 보려면 Alt 키를 누를 수 있습니다. 바로 가기 키를 보려면 디자이너에에서 열려 있는 문서나 통합 문서는 다음 단계를 수행 합니다.  
  
##### <a name="to-view-shortcut-keys-for-ribbon-tabs-and-controls-in-the-designer"></a>디자이너에서 리본 탭 및 컨트롤에 대 한 바로 가기 키를 보려면  
  
1.  Visual Studio에서에 **도구** 메뉴를 클릭 하 여 **옵션**합니다.  
  
2.  확장 된 **Office 도구** 노드를 선택한 **Microsoft Office Excel 키보드** 또는 **Microsoft Office Word 키보드**를 적절 하 게 합니다.  
  
3.  선택 **동적 키보드 구성표**합니다.  
  
     상태를 적용 하려면 변경에 대 한 Visual Studio를 다시 시작 해야 하는 메시지가 나타납니다.  
  
4.  **확인**을 클릭합니다.  
  
5.  Visual Studio를 다시 시작 하 고 프로젝트를 다시 여세요.  
  
6.  프로젝트에 대 한 문서 또는 통합 문서 디자이너를 엽니다.  
  
7.  리본 메뉴에 대 한 바로 가기 키를 표시 하려면 F6 키를 누릅니다.  
  
## <a name="accessibility-at-run-time"></a>런타임 시 내게 필요한 옵션  
  
### <a name="windows-forms-controls-on-office-documents"></a>Windows Forms Office 문서의 컨트롤  
 Windows Forms 컨트롤 내게 필요한 옵션 화면 판독기와 같은 내게 필요한 옵션 보조 기능을 제어 하는 방법에 대 한 정보를 제공 하는 속성을 노출 합니다. 문서 수준 사용자 지정에서 Office 문서에는 컨트롤이 있을 때 이러한 내게 필요한 옵션 속성을 사용할을 걸릴 수 있습니다. 자세한 내용은 참조 [Windows Form의 컨트롤에 대 한 내게 필요한 옵션 정보 제공](/dotnet/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form)합니다.  
  
 그러나 Excel 통합 문서 또는 Word 문서에 Windows Forms 컨트롤은 호스트 하는 경우 런타임 시 가지 내게 필요한 옵션 제한이 몇 가지 있습니다.  
  
-   다른 한 컨트롤에서 탭 수 없습니다.  
  
-   문서에서 컨트롤은 문서 확대/축소 설정을 100% 이외의 값으로 변경 하는 경우 비활성화 됩니다.  
  
 문서의 Windows Forms 컨트롤의 제한 사항에 대 한 정보를 참조 하십시오. [제한 Windows Forms 컨트롤의 Office 문서에](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)합니다.  
  
### <a name="actions-panes-and-custom-task-panes"></a>작업창 및 사용자 지정 작업창  
 작업 창 또는 사용자 지정 작업창에 포커스가 있을 때 컨트롤 Windows Forms 응용 프로그램에 액세스 하는 것 같은 방법으로 컨트롤 액세스할 수 있습니다. 작업 창 및 문서 간의 커서를 이동 하려면 누르면 **F6**합니다.  
  
 작업창 및 사용자 지정 작업창에 대 한 자세한 내용은 참조 [작업 창 개요](../vsto/actions-pane-overview.md) 및 [사용자 지정 작업창](../vsto/custom-task-panes.md)합니다.  
  
### <a name="display-modes"></a>디스플레이 모드  
 Visual Studio에 디스플레이 모드와 관련 된 다음과 같은 제한 사항이 있습니다.  
  
-   Word 문서 또는 Excel 워크시트에서 컨트롤은 문서 확대/축소 설정을 100% 이외의 값으로 변경 하는 경우 비활성화 됩니다.  
  
-   **새 프로젝트** 사용자 컴퓨터의 내게 필요한 옵션을 변경 하더라도 대화 상자 컨트롤을 올바르게 표시 되지 않습니다 **고대비 사용**합니다.  
  
 이러한 제한을 극복할 수 돋보기를 사용할 수 있습니다. 돋보기는 화면의 확대 부분이 표시 하는 별도 창을 만드는 windows 디스플레이 유틸리티입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션 개발](../vsto/developing-office-solutions.md)   
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [장애가 있는 사용자를 위한 접근성](/visualstudio/ide/reference/accessibility-for-people-with-disabilities)   
 [Visual Studio의 접근성 기능](/visualstudio/ide/reference/accessibility-features-of-visual-studio)  
  
  