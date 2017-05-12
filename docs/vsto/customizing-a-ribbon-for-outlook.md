---
title: "Outlook에 대해 리본 메뉴 사용자 지정"
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
  - "사용자 지정 리본, 리본 메뉴 사용자 지정 정보"
  - "리본 메뉴 사용자 지정, 리본 메뉴 사용자 지정 정보"
  - "검사기[Visual Studio에서 Office 개발]"
  - "Outlook[Visual Studio에서 Office 개발], 리본 메뉴"
  - "리본[Visual Studio에서 Office 개발], Outlook"
ms.assetid: 11d10e72-806d-4d5e-b080-139bd8633eaa
caps.latest.revision: 42
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 41
---
# Outlook에 대해 리본 메뉴 사용자 지정
  Microsoft Office Outlook에서 리본을 사용자 지정할 경우 응용 프로그램에서 사용자 지정 리본이 나타나는 위치를 고려해야 합니다.  Outlook에서 리본은 사용자가 메일 메시지 만들기 등의 특정 작업을 수행할 때 열리는 창과 기본 응용 프로그램 UI\(사용자 인터페이스\)에 표시됩니다.  이러한 응용 프로그램 창의 이름을 검사기라고 합니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.png "비디오에 링크") 관련 동영상 데모를 보려면 [어떻게 할까요?: 리본 디자이너를 사용하여 Excel의 리본 사용자 지정](http://go.microsoft.com/fwlink/?LinkID=130312)\(영문\)을 참조하세요.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## 기본 응용 프로그램 UI에 사용자 지정 리본 추가  
 Outlook의 기본 응용 프로그램 UI를 탐색기라고 합니다.  **리본\(비주얼 디자이너\)** 항목을 사용할 경우 **속성** 창에서 리본의 **RibbonType** 속성을 클릭하고 **Microsoft.Outlook.Explorer**를 선택하여 탐색기에 리본을 추가할 수 있습니다.  
  
## 검사기에 리본 할당  
 검사기에 대한 메시지 클래스에 해당하는 리본 형식을 지정하여 사용자 지정하려는 검사기를 식별합니다.  
  
 **리본\(비주얼 디자이너\)** 항목을 사용할 경우 **속성** 창에서 리본의 **RibbonType** 속성을 클릭하고 값 목록에서 리본 ID를 하나 이상 선택합니다.  
  
 프로젝트에 리본을 두 개 이상 추가할 수 있습니다.  두 개 이상의 리본이 리본 ID를 공유하는 경우 프로젝트의 `ThisAddin` 클래스에서 CreateRibbonExtensibilityObject 메서드를 재정의하여 런타임에 표시할 리본을 지정합니다.  자세한 내용은 [리본 개요](../vsto/ribbon-overview.md)을 참조하세요.  각 리본 형식에 대한 자세한 내용은 기술 문서 [Outlook 2007에서 리본 사용자 지정](http://msdn.microsoft.com/ko-kr/946e97ea-f556-4e84-8fac-01cd9214e170)을 참조하세요.  
  
## 리본 XML을 사용하여 리본 형식 지정  
 **리본\(XML\)** 항목을 사용할 경우 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> 메서드에서 *ribbonID* 매개 변수 값을 확인하고 해당하는 리본을 반환합니다.  
  
 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> 메서드는 Visual Studio를 통해 리본 코드 파일에서 자동으로 생성됩니다.  *ribbonID* 매개 변수는 탐색기 또는 특정 형식의 검사기를 식별하는 문자열입니다.  *ribbonID* 매개 변수에 대한 가능한 값의 전체 목록은 기술 문서 [Outlook 2007에서 리본 사용자 지정](http://msdn.microsoft.com/ko-kr/946e97ea-f556-4e84-8fac-01cd9214e170)을 참조하세요.  
  
 다음 코드 예제에서는 `Microsoft.Outlook.Mail.Compose` 검사기에만 사용자 지정 리본을 표시하는 방법을 보여 줍니다.  사용자가 새 메일 메시지를 만들 때 열리는 검사기입니다.  표시할 리본은 **Ribbon** 클래스에서 생성되는 `GetResourceText()` 메서드에서 지정됩니다.  **Ribbon** 클래스에 대한 자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)을 참조하세요.  
  
 [!code-csharp[Trin_RibbonOutlookBasic#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_RibbonOutlookBasic/CS/Ribbon1.cs#1)]
 [!code-vb[Trin_RibbonOutlookBasic#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_RibbonOutlookBasic/VB/Ribbon1.vb#1)]  
  
## 참고 항목  
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)   
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)  
  
  