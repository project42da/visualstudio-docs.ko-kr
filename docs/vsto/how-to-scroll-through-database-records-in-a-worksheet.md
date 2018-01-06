---
title: "방법: 워크시트에 데이터베이스 레코드 스크롤 | Microsoft Docs"
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
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
- worksheets [Office development in Visual Studio], scrolling records
ms.assetid: aea4c86c-9d6d-47dd-8977-066e21945dab
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6e3dcc6d0ed711d41fd47f043177e5d172193249
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-scroll-through-database-records-in-a-worksheet"></a>방법: 워크시트에서 데이터베이스 레코드 스크롤
  다음 절차에는 디자이너를 사용 하 여 최종 사용자 모든 레코드를 스크롤할 수 있는 컨트롤이 Microsoft Office Excel 워크시트에서 데이터베이스 테이블에서 단일 필드를 표시 하는 방법을 보여 줍니다.  
  
 문서 수준 프로젝트에만 디자이너를 사용할 수 있습니다. 그러나 또한 컨트롤을 추가한 실행 시 데이터를 프로그래밍 방식으로 바인딩할 합니다. 자세한 내용은 참조 [연습: 단순 데이터 바인딩 vsto에서 추가 기능 프로젝트에서에서](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md)합니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
### <a name="to-scroll-through-database-records-in-a-worksheet"></a>워크시트에 데이터베이스 레코드를 스크롤할 수  
  
1.  Visual Studio에서 Excel 응용 프로그램 프로젝트를 엽니다.  
  
2.  열기는 **데이터 소스** 창 데이터베이스에서 데이터 소스를 만듭니다. 자세한 내용은 참조 [새 연결 추가](../data-tools/add-new-connections.md)합니다.  
  
3.  표시 하려는 데이터가 포함 된 테이블을 확장 하 고 특정 열을 선택 합니다.  
  
4.  컨트롤 및 선택 목록을 열고이 **NamedRange**합니다.  
  
5.  끌어서는 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤 데이터를 표시 하려면 셀을 끌어옵니다.  
  
6.  **Windows Forms** 탭은 **도구 상자**, 추가 <xref:System.Windows.Forms.BindingNavigator> 워크시트에 컨트롤을 사용 하려면 컨트롤을 설정 합니다. 자세한 내용은 참조 [BindingNavigator 컨트롤 개요 &#40; Windows Forms &#41; ](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms).  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  