---
title: "Outlook 메시지 클래스에 양식 영역 연결"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VSTO.NewFormRegionWizard.InvalidMessageClassName"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "양식 영역[Visual Studio에서 Office 개발], 메시지 클래스"
  - "FormRegionMessageClassAttribute"
ms.assetid: e2db8d61-fd5f-4059-beec-33b66970f520
caps.latest.revision: 43
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 42
---
# Outlook 메시지 클래스에 양식 영역 연결
  양식 영역을 Microsoft Office Outlook의 각 항목에 대한 메시지 클래스에 연결하여 양식 영역을 표시할 Outlook 항목을 지정할 수 있습니다.  예를 들어 메일 항목의 맨 아래에 양식 영역을 추가하려면 양식 영역을 IPM.Note 메시지 클래스에 연결합니다.  
  
 양식 영역을 메시지 클래스에 연결하려면 **새 Outlook 양식 영역** 마법사에서 메시지 클래스 이름을 지정하거나 양식 영역 팩터리 클래스에 특성을 적용합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## Outlook 메시지 클래스 이해  
 Outlook 메시지 클래스는 Outlook 항목의 형식을 식별합니다.  다음 표에서는 8가지 표준 항목 형식과 각 형식의 메시지 클래스 이름을 보여 줍니다.  
  
|Outlook 항목 형식|메시지 클래스 이름|  
|-------------------|----------------|  
|AppointmentItem|IPM.Appointment|  
|ContactItem|IPM.Contact|  
|DistListItem|IPM.DistList|  
|JournalItem|IPM.Activity|  
|MailItem|IPM.Note|  
|PostItem|IPM.Post 또는 IPM.Post.RSS|  
|TaskItem|IPM.Task|  
  
 사용자 지정 메시지 클래스의 이름을 지정할 수도 있습니다.  사용자 지정 메시지 클래스는 사용자가 Outlook에서 정의한 사용자 지정 양식을 식별합니다.  
  
> [!NOTE]  
>  바꾸기 및 모두 바꾸기 양식 영역의 경우 새 사용자 지정 메시지 클래스 이름을 지정할 수 있습니다.  기존 사용자 지정 양식의 메시지 클래스 이름을 사용할 필요는 없습니다.  사용자 지정 메시지 클래스의 이름은 고유해야 합니다.  이름이 고유하도록 하는 한 가지 방법은 \<*StandardMessageClassName*\>.\<*Company*\>.\<*MessageClassName*\>과 유사한 명명 규칙\(예: IPM.Note.Contoso.MyMessageClass\)을 사용하는 것입니다.  
  
## Outlook 메시지 클래스에 양식 영역 연결  
 메시지 클래스에 양식 영역을 연결하는 방법은 다음 두 가지가 있습니다.  
  
-   **새 Outlook 양식 영역** 마법사를 사용합니다.  
  
-   클래스 특성을 적용합니다.  
  
### 새 Outlook 양식 영역 마법사 사용  
 **새 Outlook 양식 영역** 마법사의 마지막 페이지에서 표준 메시지 클래스를 선택하고 양식 영역에 연결할 사용자 지정 메시지 클래스의 이름을 입력할 수 있습니다.  
  
 양식 영역이 전체 양식 또는 양식의 기본 페이지를 바꾸기 위한 것일 경우 표준 메시지 클래스를 사용할 수 없습니다.  양식에 새 페이지를 추가하는 양식이나 양식의 맨 아래에 추가된 양식의 경우에만 표준 메시지 클래스 이름을 지정할 수 있습니다.  자세한 내용은 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)을 참조하십시오.  
  
 사용자 지정 메시지 클래스를 하나 이상 포함하려면 **이 양식 영역을 표시할 사용자 지정 메시지 클래스** 상자에 메시지 클래스 이름을 입력합니다.  
  
 다음 지침에 따라 이름을 입력해야 합니다.  
  
-   정규화된 메시지 클래스 이름\(예: "IPM.Note.Contoso"\)을 사용합니다.  
  
-   세미콜론을 사용하여 여러 개의 메시지 클래스 이름을 구분합니다.  
  
-   "IPM.Note" 또는 "IPM.Contact"와 같은 표준 Outlook 메시지 클래스를 포함하지 않습니다.  "IPM.Note.Contoso"와 같은 사용자 지정 메시지 클래스만 포함합니다.  
  
-   기본 메시지 클래스 자체\(예: "IPM"\)를 지정하지 않습니다.  
  
-   각 메시지 클래스 이름에 256자 이하를 사용합니다.  
  
 **마침**을 클릭하면 **새 Outlook 양식 영역** 마법사에서는 입력 내용의 형식에 대해 유효성을 검사합니다.  
  
> [!NOTE]  
>  **새 Outlook 양식 영역** 마법사에서는 사용자가 지정한 메시지 클래스 이름이 올바르거나 유효한지는 확인하지 않습니다.  
  
 마법사를 완료하면 **새 Outlook 양식 영역** 마법사에서는 지정한 메시지 클래스 이름이 포함된 양식 영역 클래스에 특성을 적용합니다.  이러한 특성을 사용자가 직접 적용할 수도 있습니다.  
  
### 클래스 특성 적용  
 **새 Outlook 양식 영역** 마법사를 완료한 후 Outlook 메시지 클래스에 양식 영역을 연결할 수 있습니다.  이렇게 하려면 양식 영역 팩터리 클래스에 특성을 적용합니다.  
  
 다음 예제에서는 `myFormRegion`이라는 양식 영역 팩터리 클래스에 적용된 두 개의 <xref:Microsoft.Office.Tools.Outlook.FormRegionMessageClassAttribute> 특성을 보여 줍니다.  첫 번째 특성은 메일 메시지 양식의 표준 메시지 클래스에 양식 영역을 연결합니다.  두 번째 특성은 `IPM.Task.Contoso`라는 사용자 지정 메시지 클래스에 양식 영역을 연결합니다.  
  
 [!code-csharp[Trin_Outlook_FR_Attributes#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Attributes/CS/FormRegion1.cs#1)]
 [!code-vb[Trin_Outlook_FR_Attributes#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Attributes/VB/FormRegion1.vb#1)]  
  
 다음 지침에 따라 특성을 적용해야 합니다.  
  
-   사용자 지정 메시지 클래스의 경우 정규화된 메시지 클래스 이름\(예: "IPM.Note.Contoso"\)을 사용합니다.  
  
-   기본 메시지 클래스 자체\(예: "IPM"\)를 지정하지 않습니다.  
  
-   각 메시지 클래스 이름에 256자 이하를 사용합니다.  
  
-   양식 영역이 전체 양식 또는 양식의 기본 페이지를 바꾸는 경우 표준 메시지 클래스의 이름을 포함하지 않습니다.  양식에 새 페이지를 추가하는 양식이나 양식의 맨 아래에 추가된 양식의 경우에만 표준 메시지 클래스 이름을 지정할 수 있습니다.  자세한 내용은 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)을 참조하십시오.  
  
 프로젝트를 빌드하면 Visual Studio에서는 메시지 클래스 이름의 형식에 대해 유효성을 검사합니다.  
  
> [!NOTE]  
>  Visual Studio에서는 사용자가 지정한 메시지 클래스 이름이 올바른지 또는 유효한지는 확인하지 않습니다.  
  
## 참고 항목  
 [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Outlook 양식 영역 만들기 지침](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [양식 이름과 메시지 클래스에 대 한](HV01044315)   
 [Outlook 양식과 항목 함께 작업](HV01044298)  
  
  