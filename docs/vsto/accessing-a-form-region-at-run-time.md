---
title: "런타임에 양식 영역 액세스"
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
  - "검사기[Visual Studio에서 Office 개발]"
  - "탐색기[Visual Studio에서 Office 개발]"
  - "양식 영역[Visual Studio에서 Office 개발], 런타임에 액세스"
ms.assetid: 58eaa9e0-acba-4a13-a6dd-b7e37a38156e
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# 런타임에 양식 영역 액세스
  
  
|적용 대상|  
|-----------|  
|이 항목의 정보는 다음 프로젝트 형식 및 Microsoft Office 버전에만 적용됩니다. 자세한 내용은 [Office 응용 프로그램 및 프로젝트 형식에 따라 사용 가능한 기능](../vsto/features-available-by-office-application-and-project-type.md)을 참조하세요.<br /><br /> **프로젝트 형식**<br /><br /> -   VSTO 추가 기능 프로젝트<br /><br /> **Microsoft Office 버전**<br /><br /> -   [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)]|  
  
 `Globals` 클래스를 사용하여 Outlook 프로젝트의 어디에서나 양식 영역에 액세스할 수 있습니다.`Globals` 클래스에 대한 자세한 내용은 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)를 참조하세요.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## 특정 Outlook 검사기 창에 나타나는 양식 영역 액세스  
 특정 Outlook 검사기에 나타나는 모든 양식 영역에 액세스하려면 `Globals` 클래스의 `FormRegions` 속성을 호출하고 검사기를 나타내는 <xref:Microsoft.Office.Interop.Outlook.Inspector> 개체를 전달합니다.  
  
 다음 예제에서는 현재 포커스가 있는 검사기에 나타나는 양식 영역 컬렉션을 가져옵니다. 이 예제에서는 `formRegion1`이라는 컬렉션의 양식 영역에 액세스하고 텍스트 상자에 나타나는 텍스트를 `Hello World`로 설정합니다.  
  
 [!code-csharp[Trin_Outlook_FR_Access#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Access/CS/ThisAddIn.cs#2)]
 [!code-vb[Trin_Outlook_FR_Access#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Access/VB/ThisAddIn.vb#2)]  
  
## 특정 Outlook 탐색기 창에 나타나는 양식 영역 액세스  
 특정 Outlook 탐색기에 나타나는 모든 양식 영역에 액세스하려면 `Globals` 클래스의 `FormRegions` 속성을 호출하고 탐색기를 나타내는 <xref:Microsoft.Office.Interop.Outlook.Explorer> 개체를 전달합니다.  
  
 다음 예제에서는 현재 포커스가 있는 탐색기에 나타나는 양식 영역 컬렉션을 가져옵니다. 이 예제에서는 `formRegion1`이라는 컬렉션의 양식 영역에 액세스하고 텍스트 상자에 나타나는 텍스트를 `Hello World`로 설정합니다.  
  
 [!code-csharp[Trin_Outlook_FR_Access#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Access/CS/ThisAddIn.cs#3)]
 [!code-vb[Trin_Outlook_FR_Access#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Access/VB/ThisAddIn.vb#3)]  
  
## 모든 양식 영역 액세스  
 모든 탐색기 및 모든 검사기에 나타나는 모든 양식 영역에 액세스하려면 `Globals` 클래스의 `FormRegions` 속성을 호출합니다.  
  
 다음 예제에서는 모든 탐색기 및 모든 검사기에 나타나는 양식 영역 컬렉션을 가져옵니다. 그런 다음 `formRegion1`이라는 양식 영역에 액세스하고 텍스트 상자에 나타나는 텍스트를 `Hello World`로 설정합니다.  
  
 [!code-csharp[Trin_Outlook_FR_Access#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Access/CS/ThisAddIn.cs#1)]
 [!code-vb[Trin_Outlook_FR_Access#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Access/VB/ThisAddIn.vb#1)]  
  
## 양식 영역의 컨트롤 액세스  
 `Globals` 클래스를 사용하여 양식 영역의 컨트롤에 액세스하려면 컨트롤에서 양식 영역 코드 파일 외부의 코드에 액세스할 수 있도록 만들어야 합니다.  
  
### 양식 영역 디자이너에서 디자인되는 양식 영역  
 C\#의 경우 액세스하려는 각 컨트롤의 한정자를 변경합니다. 이렇게 하려면 양식 영역 디자이너에서 각 컨트롤을 선택하고 **Modifiers** 속성을 **Internal**로 변경하거나 **속성** 창에서 **public**으로 변경합니다. 예를 들어 `textBox1`의 **Modifier** 속성을 **Internal**로 변경한 경우 `Globals.FormRegions.FormRegion1.textBox1`을 입력하여 `textBox1`에 액세스할 수 있습니다.  
  
 Visual Basic의 경우 한정자를 변경할 필요가 없습니다.  
  
### 가져온 양식 영역  
 Outlook에서 디자인된 양식 영역을 가져올 때 양식 영역에 있는 각 컨트롤의 액세스 한정자가 private으로 설정됩니다. 양식 영역 디자이너를 사용하여 가져온 양식 영역을 수정할 수 없으므로 **속성** 창에서 컨트롤의 한정자를 변경할 수 없습니다.  
  
 양식 영역 코드 파일 외부에서 컨트롤에 액세스할 수 있게 하려면 양식 영역 코드 파일 내에서 해당 컨트롤을 반환하도록 속성을 만듭니다.  
  
 C\#에서 속성을 만드는 방법에 대한 자세한 내용은 [방법: 읽기&#47;쓰기 속성 선언 및 사용&#40;C&#35; 프로그래밍 가이드&#41;](http://msdn.microsoft.com/library/a4962fef-af7e-4c4b-a929-4ae4d646ab8a)을 참조하세요.  
  
 Visual Basic에서 속성을 만드는 방법에 대한 자세한 내용은 [빌드에 없음: 방법: 클래스에 필드 및 속성 추가](http://msdn.microsoft.com/ko-kr/ae53f61b-3abc-413e-8931-703c5f5e8fc2)를 참조하세요.  
  
## 참고 항목  
 [Outlook 양식 영역 만들기 지침](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Outlook 양식 영역의 사용자 지정 작업](../vsto/custom-actions-in-outlook-form-regions.md)   
 [Outlook 메시지 클래스에 양식 영역 연결](../vsto/associating-a-form-region-with-an-outlook-message-class.md)   
 [연습: Outlook에서 디자인한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [방법: Outlook에서 양식 영역 표시하지 않기](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)   
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)  
  
  