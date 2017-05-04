---
title: "Outlook 양식 영역의 사용자 지정 작업 | Microsoft Docs"
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
  - "사용자 지정 작업[Visual Studio에서 Office 개발]"
  - "양식 영역[Visual Studio에서 Office 개발], 사용자 지정 작업"
ms.assetid: 583fd5f0-aafa-4858-9c54-38a9fdf3bede
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# Outlook 양식 영역의 사용자 지정 작업
  작업에는 사용자가 Microsoft Office Outlook 항목에 응답하는 데 사용할 수 있는 단추가 표시됩니다.  예를 들어 메일 항목에 응답하려면 **회신**, **전체 회신** 또는 **전달** 실행 단추를 클릭합니다.  이러한 각 작업은 새 메일 항목을 만들고 원래 항목의 정보를 사용하여 항목의 필드를 채웁니다.  
  
 모든 종류의 Outlook 항목을 여는 사용자 지정 작업을 만들 수 있습니다.  예를 들어 새 약속 또는 작업 항목을 여는 사용자 지정 작업을 추가할 수 있습니다.  사용자 지정 작업의 속성을 설정하거나 사용자 지정 코드를 사용하여 새 항목의 필드를 채웁니다.  사용자 지정 작업은 Outlook 검사기 창에 열려 있는 항목의 **사용자 지정 작업** 드롭다운에 나타납니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## 양식 영역에 사용자 지정 작업 추가  
 양식 영역에 사용자 지정 작업을 추가하려면 **사용자 지정 작업** 대화 상자를 사용합니다.  열 수는  **사용자 지정 작업** 대화 상자에서  **솔루션 탐색기** 확장의  **매니페스트** 노드를 선택 하는  **CustomActions** 속성 및 다음 줄임표 단추를 클릭 하 \(![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.png "ASP.NET 모바일 디자이너 줄임표")\).  
  
 **사용자 지정 작업** 대화 상자를 사용하여 *대상 양식*을 지정할 수 있습니다.  대상 양식은 사용자가 사용자 지정 작업을 실행할 때 나타나는 양식입니다.  
  
 **사용자 지정 작업** 대화 상자를 사용하여 원래 항목의 정보가 대상 양식에 나타나는 방법을 지정할 수도 있습니다.  
  
 다음 표에서는 **사용자 지정 작업** 대화 상자에서 사용할 수 있는 속성을 설명합니다.  
  
|속성|설명|  
|--------|--------|  
|**AddressLike**|대상 양식이 처리되는 방식을 지정합니다.|  
|**본문**|원래 항목의 본문이 대상 양식에 추가되는 방식을 지정합니다.|  
|**Enabled**|사용자 지정 작업을 사용할 수 있는지 여부를 나타냅니다.  이 속성이 **false**로 설정되면 사용자 지정 작업을 사용할 수 없습니다.|  
|**방법**|사용자 지정 작업이 실행될 때 사용할 수 있는 응답 유형을 지정합니다.  사용자 지정 작업에서는 양식을 보내거나, 양식을 열거나, 사용자가 양식을 보내려는지 열려는지를 확인할 수 있습니다.|  
|**이름**|코드에서 이 사용자 지정 작업을 참조하는 데 사용할 수 있는 내부 이름을 지정합니다.|  
|**ShowOnRibbon**|원래 항목의 리본 메뉴에 사용자 지정 작업을 표시할지 여부를 나타냅니다.|  
|**SubjectPrefix**|대상 양식의 제목 줄 처음에 삽입되는 텍스트를 지정합니다.|  
|**TargetForm**|대상 양식의 메시지 클래스 이름을 지정합니다.  예를 들어 작업 양식을 열려면 **IPM.Task**를 입력합니다.|  
|**제목**|사용자 지정 작업 단추의 레이블을 지정합니다.|  
  
## 런타임에 사용자 지정 작업 사용자 지정  
 코드를 사용하여 사용자 지정 작업에 동작을 추가할 수도 있습니다.  예를 들어 전자 메일 받는 사람의 이름을 가져와서 새 약속 항목의 참석자로 추가하는 코드를 추가할 수 있습니다.  이렇게 하려면 [Action](HV05247650) 개체의 [CustomAction](HV05247448) 이벤트를 처리합니다.  
  
## 참고 항목  
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Outlook 메시지 클래스에 양식 영역 연결](../vsto/associating-a-form-region-with-an-outlook-message-class.md)  
  
  