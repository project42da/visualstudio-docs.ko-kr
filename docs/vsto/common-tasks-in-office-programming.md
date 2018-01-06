---
title: "Office 프로그래밍의 일반적인 작업 | Microsoft Docs"
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
- Office development in Visual Studio, getting started
- FAQs (frequently asked questions) [Office development in Visual Studio]
- Office development in Visual Studio, frequently asked questions
ms.assetid: 7afc9bad-1d31-486e-beea-91e6d308cd67
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9f3ed53011bca8d3ab7aa4f9d6be8e619ce1b8b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="common-tasks-in-office-programming"></a>Office 프로그래밍의 일반적인 작업
  이 항목은 Visual Studio를 사용하여 Office 솔루션을 프로그래밍하는 방법에 대한 다음 범주의 일반적인 질문에 대해 답변을 찾을 수 있도록 설계되었습니다.  
  
-   [설치 및 일반 작업](#projects)  
  
-   [사용자 인터페이스 사용자 지정 작업](#ui)  
  
-   [Excel 자동화 작업](#excel)  
  
-   [Word 자동화 작업](#word)  
  
-   [데이터 작업](#data)  
  
-   [서버 쪽 문서 관리 작업](#server)  
  
-   [보안 작업](#security)  
  
-   [배포 작업](#deployment)  
  
##  <a name="projects"></a> Setup and General Tasks  
  
-   [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)합니다.  
  
-   [방법: Office 솔루션 업그레이드](http://msdn.microsoft.com/en-us/a269e539-b717-4680-a568-2152b070347e)  
  
-   [How to: Install Office Primary Interop Assemblies](../vsto/how-to-install-office-primary-interop-assemblies.md).  
  
-   [How to: Target Office Applications Through Primary Interop Assemblies](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md).  
  
-   [방법: Office 프로젝트의 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)합니다.  
  
-   [How to: Open Office Solutions without Running Code](../vsto/how-to-open-office-solutions-without-running-code.md).  
  
-   [How to: Set Up Configuration Information for an Office Solution](../vsto/how-to-set-up-configuration-information-for-an-office-solution.md).  
  
-   [How to: Show the Developer Tab on the Ribbon](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
-   [How to: Show Add-in User Interface Errors](../vsto/how-to-show-add-in-user-interface-errors.md).  
  
##  <a name="ui"></a> User Interface Customization Tasks  
  
### <a name="controls-on-documents-and-worksheets"></a>문서 및 워크시트의 컨트롤  
  
-   [How to: Add Windows Forms Controls to Office Documents](../vsto/how-to-add-windows-forms-controls-to-office-documents.md).  
  
-   [How to: Add NamedRange Controls to Worksheets](../vsto/how-to-add-namedrange-controls-to-worksheets.md).  
  
-   [How to: Add ListObject Controls to Worksheets](../vsto/how-to-add-listobject-controls-to-worksheets.md).  
  
-   [How to: Add Windows Forms Controls to Office Documents](../vsto/how-to-add-windows-forms-controls-to-office-documents.md).  
  
-   [How to: Add Content Controls to Word Documents](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
-   [How to: Add Bookmark Controls to Word Documents](../vsto/how-to-add-bookmark-controls-to-word-documents.md).  
  
### <a name="task-panes-in-document-level-customizations"></a>문서 수준 사용자 지정의 작업창  
  
-   [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)합니다.  
  
### <a name="task-panes-in-vsto-add-ins"></a>VSTO 추가 기능의 작업창  
  
-   [How to: Add a Custom Task Pane to an Application](../vsto/how-to-add-a-custom-task-pane-to-an-application.md).  
  
### <a name="ribbon-customizations"></a>리본 사용자 지정  
  
-   [How to: Get Started Customizing the Ribbon](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
-   [방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)합니다.  
  
-   [How to: Customize a Built-in Tab](../vsto/how-to-customize-a-built-in-tab.md).  
  
-   [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)합니다.  
  
-   [How to: Export a Ribbon from the Ribbon Designer to Ribbon XML](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md).  
  
### <a name="outlook-form-regions"></a>Outlook 양식 영역  
  
-   [How to: Add a Form Region to an Outlook Add-in Project](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
-   [How to: Prevent Outlook from Displaying a Form Region](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md).  
  
### <a name="custom-menus"></a>사용자 지정 메뉴  
  
-   [방법: 바로 가기 메뉴에 명령 추가](../vsto/how-to-add-commands-to-shortcut-menus.md)합니다.  
  
##  <a name="excel"></a> Excel Automation Tasks  
  
-   [방법: 프로그래밍 방식으로 워크시트 셀에 문자열을 표시](../vsto/how-to-programmatically-display-a-string-in-a-worksheet-cell.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 새 통합 문서를 만들](../vsto/how-to-programmatically-create-new-workbooks.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 통합 문서를 열고](../vsto/how-to-programmatically-open-workbooks.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 통합 문서를 저장](../vsto/how-to-programmatically-save-workbooks.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 통합 문서를 닫기](../vsto/how-to-programmatically-close-workbooks.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 통합 문서에 새 워크시트 추가](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 워크시트 숨기기](../vsto/how-to-programmatically-hide-worksheets.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 통합 문서 내에서 워크시트를 이동](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 통합 문서를 보호](../vsto/how-to-programmatically-protect-workbooks.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 코드에서 워크시트 범위 참조](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 통합 문서에서 범위에 스타일을 적용할](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 선택한 셀이 포함 된 워크시트 행의 서식 변경](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 워크시트 범위에서 텍스트 검색](../vsto/how-to-programmatically-search-for-text-in-worksheet-ranges.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 워크시트를 인쇄](../vsto/how-to-programmatically-print-worksheets.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 Excel 계산 실행](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 워크시트에서 데이터 정렬](../vsto/how-to-programmatically-sort-data-in-worksheets.md)합니다.  
  
##  <a name="word"></a> Word Automation Tasks  
  
-   [방법: 프로그래밍 방식으로 새 문서를 만들](../vsto/how-to-programmatically-create-new-documents.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 기존 문서 열기](../vsto/how-to-programmatically-open-existing-documents.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 문서를 저장](../vsto/how-to-programmatically-save-documents.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 문서를 닫기](../vsto/how-to-programmatically-close-documents.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 Word 문서에 텍스트 삽입](../vsto/how-to-programmatically-insert-text-into-word-documents.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 정의 하 고 문서에서 범위 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 문서의 범위 다시 설정 Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 문서의 텍스트 서식 지정](../vsto/how-to-programmatically-format-text-in-documents.md)합니다.  
  
-   [How to: Add XMLNode Controls to Word Documents](../vsto/how-to-add-xmlnode-controls-to-word-documents.md).  
  
-   [방법: 프로그래밍 방식으로 책갈피 텍스트 업데이트](../vsto/how-to-programmatically-update-bookmark-text.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 검색 하 고 문서에서 텍스트를 바꿀](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 문서를 인쇄](../vsto/how-to-programmatically-print-documents.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 Word 표 만들기](../vsto/how-to-programmatically-create-word-tables.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 Word 표에 행과 열을 추가](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)합니다.  
  
-   [방법: 프로그래밍 방식으로 문서의 문자 수 문서](../vsto/how-to-programmatically-count-characters-in-documents.md)합니다.  
  
##  <a name="data"></a> Data Tasks  
  
### <a name="data-bound-controls"></a>데이터 바인딩 컨트롤  
  
-   [How to: Populate Worksheets with Data from a Database](../vsto/how-to-populate-worksheets-with-data-from-a-database.md).  
  
-   [How to: Populate Documents with Data from a Database](../vsto/how-to-populate-documents-with-data-from-a-database.md).  
  
-   [How to: Populate Documents with Data from Services](../vsto/how-to-populate-documents-with-data-from-services.md).  
  
-   [How to: Populate Documents with Data from Objects](../vsto/how-to-populate-documents-with-data-from-objects.md).  
  
-   [How to: Populate Documents with Data from a Database](../vsto/how-to-populate-documents-with-data-from-a-database.md).  
  
-   [How to: Populate Documents with Data from Services](../vsto/how-to-populate-documents-with-data-from-services.md).  
  
-   [How to: Update a Data Source with Data from a Host Control](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).  
  
### <a name="cached-data-in-document-level-solutions"></a>문서 수준 솔루션의 캐시된 데이터  
  
-   [How to: Cache Data for Use Offline or on a Server](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   [How to: Programmatically Cache a Data Source in an Office Document](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md).  
  
-   [How to: Cache Data in a Password-Protected Document](../vsto/how-to-cache-data-in-a-password-protected-document.md).  
  
### <a name="custom-xml-data"></a>사용자 지정 XML 데이터  
  
-   [How to: Add Custom XML Parts to Document-Level Customizations](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md).  
  
-   [How to: Add Custom XML Parts to Documents by Using VSTO Add-Ins](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md).  
  
##  <a name="server"></a> Server-side Document Management Tasks  
  
-   [방법: 문서에서 관리 코드 확장 제거](../vsto/how-to-remove-managed-code-extensions-from-documents.md)합니다.  
  
-   [방법: 문서에 관리 코드 확장 연결](../vsto/how-to-attach-managed-code-extensions-to-documents.md)합니다.  
  
##  <a name="security"></a> Security Tasks  
  
-   [방법: Office 솔루션에 서명](../vsto/how-to-sign-office-solutions.md)합니다.  
  
##  <a name="deployment"></a> Deployment Tasks  
  
-   [방법: ClickOnce를 사용하여 Office 솔루션 게시](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)  
  
-   [방법: ClickOnce를 사용하여 SharePoint 서버에 문서 수준 Office 솔루션 게시](http://msdn.microsoft.com/en-us/2408e809-fb78-42a1-9152-00afa1522e58).  
  
-   [방법: ClickOnce Office 솔루션 설치](http://msdn.microsoft.com/en-us/14702f48-9161-4190-994c-78211fe18065).  
  
-   [방법: 최종 사용자 컴퓨터에 Office 솔루션 실행을 위한 필수 조건 설치](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98)  
  
-   [방법: Office 솔루션 배포를 위해 IIS 준비](http://msdn.microsoft.com/en-us/f62bce70-81d4-4f8b-86e6-2f2afec5d9b4).  
  
-   [방법: 배포된 Office 솔루션 업데이트](http://msdn.microsoft.com/en-us/be96db53-b6ea-46ab-b8d9-b76b098b3b13).  
  
-   [방법: Office 솔루션의 설치 경로 변경](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd).  
  
## <a name="see-also"></a>참고 항목  
 [시작 &#40; Visual Studio &#41;에서 Office 개발](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Office 응용 프로그램 및 프로젝트 형식에 따라 사용할 수 있는 기능](../vsto/features-available-by-office-application-and-project-type.md)   
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)  
  
  