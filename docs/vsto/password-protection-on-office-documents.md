---
title: "Office 문서의 암호 보호"
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
  - "문서[Visual Studio에서 Office 개발], 제한된 권한"
  - "Office 문서[Visual Studio에서 Office 개발], 제한된 권한"
  - "암호[Visual Studio에서 Office 개발], 문서 보호"
  - "권한[Visual Studio에서 Office 개발]"
  - "통합 문서[Visual Studio에서 Office 개발], 제한된 권한"
ms.assetid: 9cee99c8-73c6-4f89-9d5e-7912c876ff96
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# Office 문서의 암호 보호
  암호를 모르는 사람은 열 수 없도록 Microsoft Office Word 문서와 Microsoft Office Excel 통합 문서에 암호를 설정할 수 있습니다.  이 옵션을 **열기 암호**라고 합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 **열기 암호**가 설정된 기존 문서 및 통합 문서를 사용하여 문서 수준 프로젝트를 만들 수 있습니다.  **열기 암호**가 설정된 Word 및 Excel 문서는 Visual Studio에서 다르게 동작합니다.  
  
 **열기 암호** 설정에 대한 자세한 내용은 Word나 Excel의 도움말을 참조하십시오.  
  
## Excel 및 Word의 동작  
 Visual Studio에서 **열기 암호**가 설정된 Excel 통합 문서를 열 때마다 암호를 입력하라는 메시지가 나타납니다.  솔루션을 빌드할 때는 빌드하는 동안 문서가 열리므로 암호를 입력하라는 메시지가 다시 나타납니다.  
  
 Visual Studio에서 **열기 암호**가 설정된 Word 문서를 처음 열면 암호를 입력하라는 메시지가 나타납니다.  암호를 제대로 입력하면 문서에서 **열기 암호**가 제거되고 문서를 열 때 암호를 묻는 메시지가 더 이상 나타나지 않습니다.  솔루션에 포함된 문서를 열 때 암호를 입력하도록 설정하려면 최종 빌드 후와 솔루션 배포 전에 **열기 암호**를 설정해야 합니다.  
  
## 참고 항목  
 [문서 수준 솔루션의 문서 보호](../vsto/document-protection-in-document-level-solutions.md)   
 [정보 권한 관리 및 관리 코드 확장 개요](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [방법: 제한된 권한이 부여된 문서의 숨겨진 코드 실행 허용](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)  
  
  