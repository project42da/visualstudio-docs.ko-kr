---
title: "Visual Studio 내에서 Office 기능 사용"
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
  - "Office 응용 프로그램[Visual Studio에서 Office 개발]"
  - "Visual Studio 내의 Office 기능"
  - "보안[Visual Studio에서 Office 개발], 문서 보호"
ms.assetid: 593fd583-57e5-4ed5-8489-89f73b886c6c
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# Visual Studio 내에서 Office 기능 사용
  문서 수준 프로젝트를 만들 때는 문서를 직접 디자인하고 작업할 수 있도록 문서 및 관련 응용 프로그램이 Visual Studio 내에 호스팅됩니다.  Visual Studio에서 Microsoft Office 응용 프로그램을 열 경우 대개는 예상대로 작동합니다.  그러나 응용 프로그램의 일부 기능은 다르게 작동하거나 액세스할 수 없습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## 문서 보호  
 Microsoft Office Word 및 Microsoft Office Excel에서는 프로젝트에서 사용할 수 있는 문서 보호 기능을 제공합니다.  그러나 문서가 Visual Studio에서 열려 있는 동안 문서 보호 기능을 사용하도록 설정된 경우 일부 디자인을 변경할 수 없는 경우가 있습니다.  자세한 내용은 [문서 수준 솔루션의 문서 보호](../vsto/document-protection-in-document-level-solutions.md)을 참조하십시오.  
  
## 정보 권한 관리  
 IRM\(정보 권한 관리\)은 Microsoft Office Word 및 Microsoft Office Excel에서 사용할 수 있습니다.  IRM은 권한이 없는 사용자가 중요한 정보를 보거나 변경할 수 없도록 하는 데 유용합니다.  그러나 IRM으로 인해 코드가 실행되지 않을 수도 있습니다.  자세한 내용은 [정보 권한 관리 및 관리 코드 확장 개요](../vsto/information-rights-management-and-managed-code-extensions-overview.md)을 참조하십시오.  
  
## 암호 보호  
 암호를 모르는 사람은 열 수 없도록 Microsoft Office Word 문서와 Microsoft Office Excel 통합 문서에 암호를 설정할 수 있습니다.  암호 보호는 Word와 Excel에서 각기 다르게 처리되며 개발 프로세스에 영향을 줄 수 있습니다.  자세한 내용은 [Office 문서의 암호 보호](../vsto/password-protection-on-office-documents.md)을 참조하십시오.  
  
## 참고 항목  
 [문서 수준 솔루션의 문서 보호](../vsto/document-protection-in-document-level-solutions.md)   
 [정보 권한 관리 및 관리 코드 확장 개요](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Office 문서의 암호 보호](../vsto/password-protection-on-office-documents.md)   
 [방법: 코드를 실행하지 않고 Office 솔루션 열기](../vsto/how-to-open-office-solutions-without-running-code.md)  
  
  