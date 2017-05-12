---
title: "방법: Office 솔루션의 구성 정보 설정"
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
  - "구성 파일[Visual Studio에서 Office 개발]"
  - "솔루션[Visual Studio에서 Office 개발], 구성 파일"
ms.assetid: f123838f-957a-4cf5-acc0-0cc0f4c2aea2
caps.latest.revision: 33
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 33
---
# 방법: Office 솔루션의 구성 정보 설정
  구성 파일을 사용하여 Office 솔루션과 관련된 설정을 구성하고  어셈블리 바인딩 정책, 원격 개체, 디버그 및 추적 설정 등의 설정을 지정할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### Office 프로젝트에 구성 파일을 추가하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2.  **범주** 창에서 **일반**을 클릭합니다.  
  
3.  **템플릿** 창에서 **응용 프로그램 구성 파일**을 선택합니다.  
  
4.  **이름** 상자에서 어셈블리와 동일한 이름에 확장명 .config를 붙여 입력합니다.  예를 들어, ExcelWorkbook1.dll이라는 Excel 프로젝트 어셈블리에 대한 구성 파일의 이름은 ExcelWorkbook1.dll.config로 지정됩니다.  
  
5.  **추가**를 클릭합니다.  
  
6.  응용 프로그램 구성 파일 스키마에 따라 구성 파일을 만듭니다.  자세한 내용은 [.NET Framework의 구성 파일 스키마](http://msdn.microsoft.com/library/69003d39-dc8a-460c-a6be-e6d93e690b38)을 참조하십시오.  
  
 Office 프로젝트에서 구성 파일을 사용하는 경우 특별히 고려할 사항이 없습니다.  
  
## 참고 항목  
 [.NET Framework의 구성 파일 스키마](http://msdn.microsoft.com/library/69003d39-dc8a-460c-a6be-e6d93e690b38)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
  