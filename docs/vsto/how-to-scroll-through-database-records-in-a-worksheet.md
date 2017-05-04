---
title: "방법: 워크시트에서 데이터베이스 레코드 스크롤 | Microsoft Docs"
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
  - "데이터[Visual Studio에서 Office 개발], 데이터베이스 레코드 스크롤"
  - "데이터베이스[Visual Studio에서 Office 개발], 레코드 스크롤"
  - "레코드[Visual Studio에서 Office 개발], 스크롤"
  - "워크시트[Visual Studio에서 Office 개발], 레코드 스크롤"
ms.assetid: aea4c86c-9d6d-47dd-8977-066e21945dab
caps.latest.revision: 33
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 32
---
# 방법: 워크시트에서 데이터베이스 레코드 스크롤
  다음 절차에서는 디자이너를 사용하여 Microsoft Office Excel 워크시트에서 데이터베이스 테이블의 필드 하나를 최종 사용자가 모든 레코드를 스크롤하는 데 사용할 수 있는 컨트롤과 함께 표시하는 방법을 보여 줍니다.  
  
 문서 수준 프로젝트에서만 디자이너를 사용할 수 있습니다.  그러나 런타임에 프로그래밍 방식으로도 컨트롤을 추가하고 데이터에 바인딩할 수 있습니다.  자세한 내용은 [연습: VSTO 추가 기능 프로젝트의 단순 데이터 바인딩](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
### 워크시트에서 데이터베이스 레코드를 스크롤하려면  
  
1.  Visual Studio에서 Excel 응용 프로그램 프로젝트를 엽니다.  
  
2.  **데이터 소스** 창을 열고 데이터베이스에서 데이터 소스를 만듭니다.  자세한 내용은 [방법: 데이터베이스의 데이터에 연결](~/data-tools/how-to-connect-to-data-in-a-database.md)을 참조하십시오.  
  
3.  표시하려는 데이터가 들어 있는 테이블을 확장하고 특정 열을 선택합니다.  
  
4.  컨트롤 목록을 열고 **NamedRange**를 선택합니다.  
  
5.  데이터를 표시하려는 셀에 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 끌어 놓습니다.  
  
6.  **도구 상자**의 **Windows Forms** 탭에서 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 워크시트에 추가하고 사용할 컨트롤을 설정합니다.  자세한 내용은 [BindingNavigator 컨트롤 개요&#40;Windows Forms&#41;](http://msdn.microsoft.com/library/4423eede-f8d1-4d02-822f-5bf8432680d0)을 참조하십시오.  
  
## 참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  